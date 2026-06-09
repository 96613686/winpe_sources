# UnionFs::HandleQueryEa(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsUnionCtx &,bool *,UnionFs::StackEventTracer &)

- ea: `0x14001cc70`
- end: `0x14001d5c9`
- name: `?HandleQueryEa@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsStreamHandleCtx@1@AEAVUfsUnionCtx@1@PEA_NAEAVStackEventTracer@1@@Z`
- size: `2393`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, struct _FLT_CALLBACK_DATA *@<rdx>, const struct _FLT_RELATED_OBJECTS *@<r8>, struct UnionFs::UfsStreamHandleCtx *@<r9>, struct UnionFs::UfsUnionCtx *, bool *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x14001e950`

## callees

- `0x140006064`
- `0x14000f81c`
- `0x14001014c`
- `0x14001c888`
- `0x14001c8f8`
- `0x14001c9ac`
- `0x14001cc70`
- `0x14001f170`
- `0x140022020`
- `0x140023a10`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14006e394`
- `0x14007bbd0`
- `0x14007bf40`
- `0x1400a7008`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001cef3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001cef3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cf94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d043`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d16b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d22c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d320`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d491`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d560`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cf94`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d043`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d16b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d22c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d320`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d491`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d560`
- `ntoskrnl!KeSetEvent` at `0x14001d20c`
- `ntoskrnl!KeSetEvent` at `0x14001d300`
- `ntoskrnl!KeSetEvent` at `0x14001d46c`
- `ntoskrnl!KeSetEvent` at `0x14001d540`
- `ntoskrnl!KeSetEvent` at `0x14001d20c`
- `ntoskrnl!KeSetEvent` at `0x14001d300`
- `ntoskrnl!KeSetEvent` at `0x14001d46c`
- `ntoskrnl!KeSetEvent` at `0x14001d540`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ce06`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d2d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d442`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d516`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ce06`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d2d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d442`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d516`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ce12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d2e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d44e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d522`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ce12`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d2e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d44e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001d522`
- `FLTMGR!FltLockUserBuffer` at `0x14001ce58`
- `FLTMGR!FltLockUserBuffer` at `0x14001ce58`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001cd19`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001ceba`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d075`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d19d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d262`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d356`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d4cc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d596`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001cd19`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001ceba`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d075`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d19d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d262`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d356`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d4cc`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001d596`

## string_xrefs

- `0x14001d3b5`: `PUSH: Copying EAs to buffer`
- `0x14001d400`: `ORIGIN: Copy EAs into user buffer`

## pseudocode

```c
__int64 __fastcall UnionFs::HandleQueryEa(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_RELATED_OBJECTS *a3,
        struct UnionFs::UfsStreamHandleCtx *a4,
        struct UnionFs::UfsUnionCtx *a5,
        struct UnionFs::StackEventTracer *a6)
{
  void *v9; // r15
  struct UnionFs::StackEventTracer *v10; // rsi
  int v11; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v12; // rcx
  UnionFs::UfsEaTable *v14; // rcx
  utl::_RefCountBase *v15; // rbx
  utl::_RefCountBase *v16; // r12
  struct _ERESOURCE *Length; // rcx
  PFLT_IO_PARAMETER_BLOCK Iopb; // r14
  unsigned int v19; // edi
  struct _FLT_FILE_NAME_INFORMATION *v20; // rcx
  LARGE_INTEGER AllocationSize; // rcx
  PVOID v22; // rax
  const char *v23; // rax
  __int64 v24; // r8
  unsigned __int64 v25; // rax
  PVOID EaBuffer; // r9
  void **v27; // rax
  void *v28; // rdi
  int v29; // edx
  unsigned int v30; // esi
  struct _FLT_FILE_NAME_INFORMATION *v31; // rcx
  PVOID EaList; // rcx
  int v33; // edx
  int EaInfoBuffer; // r12d
  struct _FLT_FILE_NAME_INFORMATION *v35; // rcx
  const struct _FLT_RELATED_OBJECTS *v36; // r13
  ULONG EaLength; // eax
  struct _FLT_FILE_NAME_INFORMATION *v38; // rcx
  unsigned int FileObject; // eax
  struct _ERESOURCE *v40; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v41; // rcx
  int EAs; // eax
  unsigned int v43; // r13d
  struct _ERESOURCE *v44; // rcx
  bool v45; // zf
  struct _FLT_FILE_NAME_INFORMATION *v46; // rcx
  const char *Priority; // [rsp+28h] [rbp-C0h]
  const char *Prioritya; // [rsp+28h] [rbp-C0h]
  const char *Priorityb; // [rsp+28h] [rbp-C0h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+40h] [rbp-A8h] BYREF
  UCHAR OperationFlags; // [rsp+48h] [rbp-A0h]
  char v52[15]; // [rsp+49h] [rbp-9Fh] BYREF
  utl::_RefCountBase *v53[2]; // [rsp+58h] [rbp-90h] BYREF
  PERESOURCE Resource; // [rsp+68h] [rbp-80h]
  __m128i si128; // [rsp+70h] [rbp-78h] BYREF
  __int64 Pointer; // [rsp+80h] [rbp-68h]
  PVOID P[2]; // [rsp+90h] [rbp-58h] BYREF
  unsigned __int64 v58; // [rsp+A0h] [rbp-48h] BYREF
  PVOID v59; // [rsp+A8h] [rbp-40h]
  PVOID v60; // [rsp+B0h] [rbp-38h]
  utl::_RefCountBase *v61; // [rsp+B8h] [rbp-30h]
  unsigned int v62; // [rsp+F8h] [rbp+10h] BYREF
  const struct _FLT_RELATED_OBJECTS *v63; // [rsp+100h] [rbp+18h]

  v63 = a3;
  v9 = 0;
  *(_BYTE *)a5 = 0;
  FileNameInformation = 0;
  si128.m128i_i64[0] = 0;
  si128.m128i_i64[1] = a2->IoStatus.Information;
  Pointer = (__int64)a2->IoStatus.Pointer;
  v10 = a6;
  v11 = UnionFs::Utils::GetFileNameInformation(&si128, 16777473, &FileNameInformation, a6);
  if ( v11 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v11,
      (int)v10,
      (struct UnionFs::StackEventTracer *)0x53500050075LL,
      (unsigned __int64)"UnionFs::HandleQueryEa",
      "PUSH: Getting source file name information",
      Priority);
LABEL_3:
    v12 = FileNameInformation;
    FileNameInformation = 0;
    if ( v12 )
      FltReleaseFileNameInformation(v12);
    return (unsigned int)v11;
  }
  *(_OWORD *)v53 = 0;
  Resource = 0;
  if ( *((_DWORD *)a4 + 7) == 2 )
    v14 = *(UnionFs::UfsEaTable **)(*((_QWORD *)a4 + 4) + 24LL);
  else
    v14 = (UnionFs::UfsEaTable *)*((_QWORD *)UnionFs::g_FilterState + 11);
  v11 = UnionFs::UfsEaTable::LookupEaEntry(
          v14,
          (const struct _FLT_INSTANCE *)a2->IoStatus.Pointer,
          FileNameInformation,
          0,
          (struct UnionFs::LookupEaResults *)v53,
          v10);
  if ( v11 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v11,
      (int)v10,
      (struct UnionFs::StackEventTracer *)0x5600005007FLL,
      (unsigned __int64)"UnionFs::HandleQueryEa",
      "PUSH: EA table lookup",
      Prioritya);
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v53);
    goto LABEL_3;
  }
  v15 = v53[1];
  v61 = v53[1];
  if ( v53[1] )
    _InterlockedIncrement((volatile signed __int32 *)v53[1] + 2);
  v16 = v53[0];
  if ( !v53[0] )
  {
    if ( v15 )
      utl::_RefCountBase::_DecStrong(v15);
LABEL_92:
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v53);
    v41 = FileNameInformation;
    FileNameInformation = 0;
    if ( v41 )
      FltReleaseFileNameInformation(v41);
    return 0;
  }
  Length = Resource;
  Resource = 0;
  if ( Length )
  {
    ExReleaseResourceLite(Length);
    KeLeaveCriticalRegion();
  }
  Iopb = CallbackData->Iopb;
  OperationFlags = Iopb->OperationFlags;
  LOBYTE(Length) = (OperationFlags & 2) != 0;
  v52[1] = (char)Length;
  LOBYTE(v62) = OperationFlags & 4;
  v52[0] = (OperationFlags & 4) != 0;
  v60 = 0;
  if ( Iopb->Parameters.Create.AllocationSize.QuadPart )
  {
    v19 = FltLockUserBuffer(CallbackData);
    if ( (v19 & 0x80000000) != 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)v19,
        (int)v10,
        (struct UnionFs::StackEventTracer *)0x5360005009DLL,
        (unsigned __int64)"UnionFs::HandleQueryEa",
        "API: FltLockUserBuffer",
        Prioritya);
LABEL_22:
      if ( v15 )
        utl::_RefCountBase::_DecStrong(v15);
      UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v53);
      v20 = FileNameInformation;
      FileNameInformation = 0;
      if ( v20 )
        FltReleaseFileNameInformation(v20);
      return v19;
    }
    AllocationSize = Iopb->Parameters.Create.AllocationSize;
    if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
      v22 = *(PVOID *)(AllocationSize.QuadPart + 24);
    else
      v22 = MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x40000010u);
    if ( v22 )
    {
      v23 = "ORIGIN: MmGetSystemAddressForMdlSafe";
      v24 = 0x537000500A6LL;
      v19 = -1073741801;
LABEL_32:
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)v19,
        (int)v10,
        (struct UnionFs::StackEventTracer *)v24,
        (unsigned __int64)"UnionFs::HandleQueryEa",
        v23,
        Prioritya);
      goto LABEL_22;
    }
    Length = (struct _ERESOURCE *)Iopb->Parameters.Read.Length;
    if ( !(_DWORD)Length )
    {
      v58 = Iopb->Parameters.Read.Length;
      v59 = 0;
      v25 = 0;
      EaBuffer = 0;
LABEL_44:
      v28 = 0;
      goto LABEL_45;
    }
    goto LABEL_113;
  }
  v25 = Iopb->Parameters.Read.Length;
  if ( !CallbackData->RequestorMode )
  {
    EaBuffer = Iopb->Parameters.Create.EaBuffer;
    if ( EaBuffer || !(_DWORD)v25 )
    {
      v58 = Iopb->Parameters.Read.Length;
      v59 = EaBuffer;
      LODWORD(Length) = v25;
      goto LABEL_44;
    }
LABEL_113:
    gsl::details::terminate((gsl::details *)Length);
    JUMPOUT(0x14001D5C9LL);
  }
  v27 = (void **)utl::make_unique_pool<enum gsl::byte [0],256,1634027093,0>(P, (unsigned int)v25);
  v9 = *v27;
  *v27 = 0;
  v60 = v9;
  if ( P[0] )
    ExFreePoolWithTag(P[0], 0);
  if ( !v9 )
  {
    v23 = "ORIGIN: Allocating EA double buffer";
    v24 = 0x641000500B7LL;
    v19 = -1073741670;
    goto LABEL_32;
  }
  v25 = Iopb->Parameters.Read.Length;
  v58 = v25;
  v59 = v9;
  v28 = v9;
  LODWORD(Length) = v25;
  EaBuffer = v9;
LABEL_45:
  if ( v25 < 0xC )
  {
    v29 = (int)v10;
    v30 = -1073741820;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000004LL,
      v29,
      (struct UnionFs::StackEventTracer *)0x539000500C6LL,
      (unsigned __int64)"UnionFs::HandleQueryEa",
      "ORIGIN: Provided buffer too small",
      Prioritya);
LABEL_47:
    if ( v28 )
      ExFreePoolWithTag(v28, 0);
    if ( v15 )
      utl::_RefCountBase::_DecStrong(v15);
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v53);
    v31 = FileNameInformation;
    FileNameInformation = 0;
    if ( v31 )
      FltReleaseFileNameInformation(v31);
    return v30;
  }
  memset(EaBuffer, 0, (unsigned int)Length);
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  Pointer = -1;
  if ( Iopb->Parameters.Read.ByteOffset.LowPart )
  {
    EaList = Iopb->Parameters.QueryEa.EaList;
    if ( !EaList )
    {
      v33 = (int)v10;
      v30 = -2147483628;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0x80000014LL,
        v33,
        (struct UnionFs::StackEventTracer *)0x53A000500D3LL,
        (unsigned __int64)"UnionFs::HandleQueryEa",
        "ORIGIN: EaList is null",
        Prioritya);
      utl::vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(&si128);
      goto LABEL_47;
    }
    P[0] = (PVOID)Iopb->Parameters.Read.ByteOffset.LowPart;
    P[1] = EaList;
    EaInfoBuffer = UnionFs::GetNamesFromGetEaInfoBuffer(P, &si128, v10);
    if ( EaInfoBuffer < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)EaInfoBuffer,
        (int)v10,
        (struct UnionFs::StackEventTracer *)0x53C000500DCLL,
        (unsigned __int64)"UnionFs::HandleQueryEa",
        "PUSH: Getting EA names from ea list buffer",
        Prioritya);
      utl::vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(&si128);
      if ( v28 )
        ExFreePoolWithTag(v28, 0);
      if ( v15 )
        utl::_RefCountBase::_DecStrong(v15);
      UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v53);
      v35 = FileNameInformation;
      FileNameInformation = 0;
      if ( v35 )
        FltReleaseFileNameInformation(v35);
      return (unsigned int)EaInfoBuffer;
    }
    v16 = v53[0];
  }
  v36 = v63;
  UnionFs::UfsStreamHandleCtx::SynchronizeQueryEa(v63, P);
  if ( (si128.m128i_i64[1] - si128.m128i_i64[0]) >> 4 )
  {
LABEL_81:
    FileObject = 0;
    goto LABEL_83;
  }
  if ( !(_BYTE)v62 )
  {
    if ( (OperationFlags & 1) == 0 )
    {
      FileObject = (unsigned int)v36[15].FileObject;
      goto LABEL_83;
    }
    LODWORD(v36[15].FileObject) = 0;
    goto LABEL_81;
  }
  EaLength = Iopb->Parameters.Create.EaLength;
  if ( !EaLength )
  {
    if ( P[0] )
      KeSetEvent((PRKEVENT)P[0], 0, 0);
    utl::vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(&si128);
    if ( v28 )
      ExFreePoolWithTag(v28, 0);
    if ( v15 )
      utl::_RefCountBase::_DecStrong(v15);
    UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v53);
    v38 = FileNameInformation;
    FileNameInformation = 0;
    if ( v38 )
      FltReleaseFileNameInformation(v38);
    return 3221225553LL;
  }
  FileObject = EaLength - 1;
LABEL_83:
  v62 = FileObject;
  (*(void (__fastcall **)(utl::_RefCountBase *, char *))(*(_QWORD *)v16 + 8LL))(v16, &v52[7]);
  if ( !*((_BYTE *)v16 + 8) )
  {
    v40 = *(struct _ERESOURCE **)&v52[7];
    *(_QWORD *)&v52[7] = 0;
    if ( v40 )
    {
      ExReleaseResourceLite(v40);
      KeLeaveCriticalRegion();
    }
    if ( P[0] )
      KeSetEvent((PRKEVENT)P[0], 0, 0);
    utl::vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(&si128);
    if ( v28 )
      ExFreePoolWithTag(v28, 0);
    if ( v15 )
      utl::_RefCountBase::_DecStrong(v15);
    goto LABEL_92;
  }
  EAs = UnionFs::UfsEaPayload::GetEAs((__int64)v16, v52[1], &v58, &v62, (const STRING **)&si128, v52[0], 0);
  v43 = EAs;
  if ( EAs == -2147483630 || (unsigned int)(EAs + 1073741743) <= 1 || EAs >= 0 )
  {
    if ( v28 )
      RtlCopyToUser(Iopb->Parameters.Create.EaBuffer, v28, Iopb->Parameters.Read.Length);
    LODWORD(v63[15].FileObject) = v62;
    *(_BYTE *)a5 = 1;
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)EAs,
      (int)v10,
      (struct UnionFs::StackEventTracer *)0x5630005010CLL,
      (unsigned __int64)"UnionFs::HandleQueryEa",
      "PUSH: Copying EAs to buffer",
      Priorityb);
  }
  v44 = *(struct _ERESOURCE **)&v52[7];
  v45 = *(_QWORD *)&v52[7] == 0;
  *(_QWORD *)&v52[7] = 0;
  if ( !v45 )
  {
    ExReleaseResourceLite(v44);
    KeLeaveCriticalRegion();
  }
  if ( P[0] )
    KeSetEvent((PRKEVENT)P[0], 0, 0);
  utl::vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&void RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(&si128);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( v15 )
    utl::_RefCountBase::_DecStrong(v15);
  UnionFs::LookupEaResults::~LookupEaResults((UnionFs::LookupEaResults *)v53);
  v46 = FileNameInformation;
  v45 = FileNameInformation == 0;
  FileNameInformation = 0;
  if ( !v45 )
    FltReleaseFileNameInformation(v46);
  return v43;
}

```

## disassembly

```asm
0x14001cc70  mov     r11, rsp
0x14001cc73  mov     [r11+8], rbx
0x14001cc77  mov     [r11+20h], rsi
0x14001cc7b  mov     [r11+18h], r8
0x14001cc7f  push    rdi
0x14001cc80  push    r12
0x14001cc82  push    r13
0x14001cc84  push    r14
0x14001cc86  push    r15
0x14001cc88  sub     rsp, 0C0h
0x14001cc8f  mov     rdi, r9
0x14001cc92  mov     r14, rdx
0x14001cc95  mov     r13, rcx
0x14001cc98  xor     r15d, r15d
0x14001cc9b  mov     rax, [rsp+0E8h+arg_20]
0x14001cca3  mov     [rax], r15b
0x14001cca6  mov     [rsp+0E8h+FileNameInformation], r15
0x14001ccab  mov     [r11-78h], r15
0x14001ccaf  mov     rax, [rdx+20h]
0x14001ccb3  mov     [r11-70h], rax
0x14001ccb7  mov     rax, [rdx+18h]
0x14001ccbb  mov     [r11-68h], rax
0x14001ccbf  mov     rsi, [rsp+0E8h+arg_28]
0x14001ccc7  mov     r9, rsi
0x14001ccca  lea     r8, [rsp+0E8h+FileNameInformation]
0x14001cccf  mov     edx, 1000101h
0x14001ccd4  lea     rcx, [r11-78h]
0x14001ccd8  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x14001ccdd  mov     ebx, eax
0x14001ccdf  test    eax, eax
0x14001cce1  jns     short loc_14001CD2C
0x14001cce3  lea     rax, aPushGettingSou_0; "PUSH: Getting source file name informat"...
0x14001ccea  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001ccef  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001ccf6  mov     r8, 53500050075h; struct UnionFs::StackEventTracer *
0x14001cd00  mov     rdx, rsi; int
0x14001cd03  mov     ecx, ebx; this
0x14001cd05  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001cd0a  mov     rcx, [rsp+0E8h+FileNameInformation]; FileNameInformation
0x14001cd0f  mov     [rsp+0E8h+FileNameInformation], r15
0x14001cd14  test    rcx, rcx
0x14001cd17  jz      short loc_14001CD25
0x14001cd19  call    cs:__imp_FltReleaseFileNameInformation
0x14001cd20  nop     dword ptr [rax+rax+00h]
0x14001cd25  mov     eax, ebx
0x14001cd27  jmp     loc_14001D5A5
0x14001cd2c  xorps   xmm0, xmm0
0x14001cd2f  movdqu  xmmword ptr [rsp+0E8h+var_90], xmm0
0x14001cd35  mov     [rsp+0E8h+Resource], r15
0x14001cd3a  cmp     dword ptr [rdi+1Ch], 2
0x14001cd3e  jnz     short loc_14001CD4A
0x14001cd40  mov     rax, [rdi+20h]
0x14001cd44  mov     rcx, [rax+18h]
0x14001cd48  jmp     short loc_14001CD55
0x14001cd4a  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001cd51  mov     rcx, [rax+58h]; this
0x14001cd55  mov     qword ptr [rsp+0E8h+Priority], rsi; char *
0x14001cd5a  lea     rax, [rsp+0E8h+var_90]
0x14001cd5f  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; struct UnionFs::LookupEaResults *
0x14001cd64  xor     r9d, r9d; bool
0x14001cd67  mov     r8, [rsp+0E8h+FileNameInformation]; struct _FLT_FILE_NAME_INFORMATION *
0x14001cd6c  mov     rdx, [r14+18h]; struct _FLT_INSTANCE *
0x14001cd70  call    ?LookupEaEntry@UfsEaTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@_NAEAULookupEaResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsEaTable::LookupEaEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,bool,UnionFs::LookupEaResults &,UnionFs::StackEventTracer &)
0x14001cd75  mov     ebx, eax
0x14001cd77  test    eax, eax
0x14001cd79  jns     short loc_14001CDB1
0x14001cd7b  lea     rax, aPushEaTableLoo; "PUSH: EA table lookup"
0x14001cd82  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001cd87  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001cd8e  mov     r8, 5600005007Fh; struct UnionFs::StackEventTracer *
0x14001cd98  mov     rdx, rsi; int
0x14001cd9b  mov     ecx, ebx; this
0x14001cd9d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001cda2  lea     rcx, [rsp+0E8h+var_90]; this
0x14001cda7  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001cdac  jmp     loc_14001CD0A
0x14001cdb1  mov     rbx, [rsp+0E8h+var_90+8]
0x14001cdb6  mov     [rsp+0E8h+var_30], rbx
0x14001cdbe  test    rbx, rbx
0x14001cdc1  jz      short loc_14001CDC7
0x14001cdc3  lock inc dword ptr [rbx+8]
0x14001cdc7  mov     r12, [rsp+0E8h+var_90]
0x14001cdcc  test    r12, r12
0x14001cdcf  jnz     short loc_14001CDF7
0x14001cdd1  test    rbx, rbx
0x14001cdd4  jz      short loc_14001CDDE
0x14001cdd6  mov     rcx, rbx; this
0x14001cdd9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001cdde  lea     rcx, [rsp+0E8h+var_90]; this
0x14001cde3  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001cde8  mov     rcx, [rsp+0E8h+FileNameInformation]
0x14001cded  mov     [rsp+0E8h+FileNameInformation], r15
0x14001cdf2  jmp     loc_14001D351
0x14001cdf7  mov     rcx, [rsp+0E8h+Resource]; Resource
0x14001cdfc  mov     [rsp+0E8h+Resource], r15
0x14001ce01  test    rcx, rcx
0x14001ce04  jz      short loc_14001CE1E
0x14001ce06  call    cs:__imp_ExReleaseResourceLite
0x14001ce0d  nop     dword ptr [rax+rax+00h]
0x14001ce12  call    cs:__imp_KeLeaveCriticalRegion
0x14001ce19  nop     dword ptr [rax+rax+00h]
0x14001ce1e  mov     r14, [r13+10h]
0x14001ce22  mov     al, [r14+6]
0x14001ce26  mov     [rsp+0E8h+var_A0], al
0x14001ce2a  mov     cl, al
0x14001ce2c  shr     cl, 1
0x14001ce2e  and     cl, 1
0x14001ce31  mov     [rsp+0E8h+var_9F+1], cl
0x14001ce35  and     al, 4
0x14001ce37  mov     byte ptr [rsp+0E8h+arg_8], al
0x14001ce3e  setnz   [rsp+0E8h+var_9F]
0x14001ce43  mov     [rsp+0E8h+var_38], r15
0x14001ce4b  cmp     [r14+40h], r15
0x14001ce4f  jz      loc_14001CF5B
0x14001ce55  mov     rcx, r13; CallbackData
0x14001ce58  call    cs:__imp_FltLockUserBuffer
0x14001ce5f  nop     dword ptr [rax+rax+00h]
0x14001ce64  mov     edi, eax
0x14001ce66  xor     r13d, r13d
0x14001ce69  test    eax, eax
0x14001ce6b  jns     short loc_14001CECD
0x14001ce6d  lea     rax, aApiFltlockuser; "API: FltLockUserBuffer"
0x14001ce74  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001ce79  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001ce80  mov     r8, 5360005009Dh; struct UnionFs::StackEventTracer *
0x14001ce8a  mov     rdx, rsi; int
0x14001ce8d  mov     ecx, edi; this
0x14001ce8f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001ce94  test    rbx, rbx
0x14001ce97  jz      short loc_14001CEA1
0x14001ce99  mov     rcx, rbx; this
0x14001ce9c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001cea1  lea     rcx, [rsp+0E8h+var_90]; this
0x14001cea6  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001ceab  mov     rcx, [rsp+0E8h+FileNameInformation]; FileNameInformation
0x14001ceb0  mov     [rsp+0E8h+FileNameInformation], r13
0x14001ceb5  test    rcx, rcx
0x14001ceb8  jz      short loc_14001CEC6
0x14001ceba  call    cs:__imp_FltReleaseFileNameInformation
0x14001cec1  nop     dword ptr [rax+rax+00h]
0x14001cec6  mov     eax, edi
0x14001cec8  jmp     loc_14001D5A5
0x14001cecd  mov     rcx, [r14+40h]; MemoryDescriptorList
0x14001ced1  test    byte ptr [rcx+0Ah], 5
0x14001ced5  jz      short loc_14001CEDD
0x14001ced7  mov     rax, [rcx+18h]
0x14001cedb  jmp     short loc_14001CEFF
0x14001cedd  mov     [rsp+0E8h+Priority], 40000010h; char *
0x14001cee5  mov     [rsp+0E8h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x14001ceea  xor     r9d, r9d; RequestedAddress
0x14001ceed  xor     edx, edx; AccessMode
0x14001ceef  lea     r8d, [r9+1]; CacheType
0x14001cef3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001cefa  nop     dword ptr [rax+rax+00h]
0x14001ceff  test    rax, rax
0x14001cf02  jz      short loc_14001CF35
0x14001cf04  lea     rax, aOriginMmgetsys; "ORIGIN: MmGetSystemAddressForMdlSafe"
0x14001cf0b  mov     r8, 537000500A6h; struct UnionFs::StackEventTracer *
0x14001cf15  mov     edi, 0C0000017h
0x14001cf1a  mov     rdx, rsi; int
0x14001cf1d  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001cf24  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001cf29  mov     ecx, edi; this
0x14001cf2b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001cf30  jmp     loc_14001CE94
0x14001cf35  mov     ecx, [r14+18h]; this
0x14001cf39  test    ecx, ecx
0x14001cf3b  jnz     loc_14001D5C3
0x14001cf41  mov     [rsp+0E8h+var_48], rcx
0x14001cf49  mov     [rsp+0E8h+var_40], r13
0x14001cf51  mov     eax, ecx
0x14001cf53  mov     r9, r13
0x14001cf56  jmp     loc_14001D004
0x14001cf5b  mov     eax, [r14+18h]
0x14001cf5f  cmp     [r13+50h], r15b
0x14001cf63  jz      short loc_14001CFDE
0x14001cf65  mov     edx, eax
0x14001cf67  lea     rcx, [rsp+0E8h+P]
0x14001cf6f  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GBGFEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1634027093,0>(unsigned __int64)
0x14001cf74  mov     r15, [rax]
0x14001cf77  xor     r13d, r13d
0x14001cf7a  mov     [rax], r13
0x14001cf7d  mov     [rsp+0E8h+var_38], r15
0x14001cf85  mov     rcx, [rsp+0E8h+P]; P
0x14001cf8d  test    rcx, rcx
0x14001cf90  jz      short loc_14001CFA0
0x14001cf92  xor     edx, edx; Tag
0x14001cf94  call    cs:__imp_ExFreePoolWithTag
0x14001cf9b  nop     dword ptr [rax+rax+00h]
0x14001cfa0  test    r15, r15
0x14001cfa3  jnz     short loc_14001CFC0
0x14001cfa5  lea     rax, aOriginAllocati_92; "ORIGIN: Allocating EA double buffer"
0x14001cfac  mov     r8, 641000500B7h
0x14001cfb6  mov     edi, 0C000009Ah
0x14001cfbb  jmp     loc_14001CF1A
0x14001cfc0  mov     eax, [r14+18h]
0x14001cfc4  mov     [rsp+0E8h+var_48], rax
0x14001cfcc  mov     [rsp+0E8h+var_40], r15
0x14001cfd4  mov     rdi, r15
0x14001cfd7  mov     ecx, eax
0x14001cfd9  mov     r9, r15
0x14001cfdc  jmp     short loc_14001D007
0x14001cfde  mov     r9, [r14+38h]
0x14001cfe2  xor     r13d, r13d
0x14001cfe5  test    r9, r9
0x14001cfe8  jnz     short loc_14001CFF2
0x14001cfea  test    eax, eax
0x14001cfec  jnz     loc_14001D5C3
0x14001cff2  mov     [rsp+0E8h+var_48], rax
0x14001cffa  mov     [rsp+0E8h+var_40], r9
0x14001d002  mov     ecx, eax
0x14001d004  mov     rdi, r13
0x14001d007  cmp     rax, 0Ch
0x14001d00b  jnb     short loc_14001D088
0x14001d00d  lea     rax, aOriginProvided; "ORIGIN: Provided buffer too small"
0x14001d014  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001d019  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001d020  mov     r8, 539000500C6h; struct UnionFs::StackEventTracer *
0x14001d02a  mov     rdx, rsi; int
0x14001d02d  mov     esi, 0C0000004h
0x14001d032  mov     ecx, esi; this
0x14001d034  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d039  test    rdi, rdi
0x14001d03c  jz      short loc_14001D04F
0x14001d03e  xor     edx, edx; Tag
0x14001d040  mov     rcx, rdi; P
0x14001d043  call    cs:__imp_ExFreePoolWithTag
0x14001d04a  nop     dword ptr [rax+rax+00h]
0x14001d04f  test    rbx, rbx
0x14001d052  jz      short loc_14001D05C
0x14001d054  mov     rcx, rbx; this
0x14001d057  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001d05c  lea     rcx, [rsp+0E8h+var_90]; this
0x14001d061  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001d066  mov     rcx, [rsp+0E8h+FileNameInformation]; FileNameInformation
0x14001d06b  mov     [rsp+0E8h+FileNameInformation], r13
0x14001d070  test    rcx, rcx
0x14001d073  jz      short loc_14001D081
0x14001d075  call    cs:__imp_FltReleaseFileNameInformation
0x14001d07c  nop     dword ptr [rax+rax+00h]
0x14001d081  mov     eax, esi
0x14001d083  jmp     loc_14001D5A5
0x14001d088  mov     r8d, ecx; Size
0x14001d08b  xor     edx, edx; Val
0x14001d08d  mov     rcx, r9; void *
0x14001d090  call    memset
0x14001d095  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001d09d  movdqu  [rsp+0E8h+var_78], xmm0
0x14001d0a3  mov     [rsp+0E8h+var_68], 0FFFFFFFFFFFFFFFFh
0x14001d0af  mov     eax, [r14+28h]
0x14001d0b3  test    eax, eax
0x14001d0b5  jz      loc_14001D1B6
0x14001d0bb  mov     rcx, [r14+20h]
0x14001d0bf  test    rcx, rcx
0x14001d0c2  jnz     short loc_14001D0FF
0x14001d0c4  lea     rax, aOriginEalistIs; "ORIGIN: EaList is null"
0x14001d0cb  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001d0d0  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001d0d7  mov     r8, 53A000500D3h; struct UnionFs::StackEventTracer *
0x14001d0e1  mov     rdx, rsi; int
0x14001d0e4  mov     esi, 80000014h
0x14001d0e9  mov     ecx, esi; this
0x14001d0eb  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d0f0  lea     rcx, [rsp+0E8h+var_78]
0x14001d0f5  call    ??1?$vector@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@@utl@@@utl@@QEAA@XZ; utl::vector<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(void)
0x14001d0fa  jmp     loc_14001D039
0x14001d0ff  mov     [rsp+0E8h+P], rax
0x14001d107  mov     [rsp+0E8h+var_50], rcx
0x14001d10f  mov     r8, rsi
0x14001d112  lea     rdx, [rsp+0E8h+var_78]
0x14001d117  lea     rcx, [rsp+0E8h+P]
0x14001d11f  call    ?GetNamesFromGetEaInfoBuffer@UnionFs@@YAJAEAV?$span@W4byte@gsl@@$0?0@gsl@@AEAV?$vector@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@@utl@@@utl@@AEAVStackEventTracer@1@@Z; UnionFs::GetNamesFromGetEaInfoBuffer(gsl::span<gsl::byte,-1> &,utl::vector<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>> &,UnionFs::StackEventTracer &)
0x14001d124  mov     r12d, eax
0x14001d127  test    eax, eax
0x14001d129  jns     loc_14001D1B1
0x14001d12f  lea     rax, aPushGettingEaN; "PUSH: Getting EA names from ea list buf"...
0x14001d136  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], rax; char *
0x14001d13b  lea     r9, aUnionfsHandleq; "UnionFs::HandleQueryEa"
0x14001d142  mov     r8, 53C000500DCh; struct UnionFs::StackEventTracer *
0x14001d14c  mov     rdx, rsi; int
0x14001d14f  mov     ecx, r12d; this
0x14001d152  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001d157  lea     rcx, [rsp+0E8h+var_78]
0x14001d15c  call    ??1?$vector@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@U_STRING@@$$A6AXPEAU1@@Z$1?RtlFreeAnsiString@@YAX0@Z$$T$0A@@wil@@@utl@@@utl@@QEAA@XZ; utl::vector<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>::~vector<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>,utl::allocator<wil::unique_struct<_STRING,void (_STRING *),&RtlFreeAnsiString(_STRING *),std::nullptr_t,0>>>(void)
0x14001d161  test    rdi, rdi
0x14001d164  jz      short loc_14001D177
0x14001d166  xor     edx, edx; Tag
0x14001d168  mov     rcx, rdi; P
0x14001d16b  call    cs:__imp_ExFreePoolWithTag
0x14001d172  nop     dword ptr [rax+rax+00h]
0x14001d177  test    rbx, rbx
0x14001d17a  jz      short loc_14001D184
0x14001d17c  mov     rcx, rbx; this
0x14001d17f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001d184  lea     rcx, [rsp+0E8h+var_90]; this
0x14001d189  call    ??1LookupEaResults@UnionFs@@QEAA@XZ; UnionFs::LookupEaResults::~LookupEaResults(void)
0x14001d18e  mov     rcx, [rsp+0E8h+FileNameInformation]; FileNameInformation
0x14001d193  mov     [rsp+0E8h+FileNameInformation], r13
0x14001d198  test    rcx, rcx
0x14001d19b  jz      short loc_14001D1A9
  ... truncated ...
```
