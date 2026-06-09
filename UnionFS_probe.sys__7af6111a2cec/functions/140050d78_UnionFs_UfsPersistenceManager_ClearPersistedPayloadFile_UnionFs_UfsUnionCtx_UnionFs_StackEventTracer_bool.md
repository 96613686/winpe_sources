# UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile(UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &,bool)

- ea: `0x140050d78`
- end: `0x140051627`
- name: `?ClearPersistedPayloadFile@UfsPersistenceManager@UnionFs@@QEBAJAEAVUfsUnionCtx@2@AEAVStackEventTracer@2@_N@Z`
- size: `2223`
- prototype: `int(UnionFs::UfsPersistenceManager *__hidden this, struct UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *, bool)`
- caller_count: `4`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400204a0`
- `0x140053518`
- `0x14005c250`
- `0x140062e54`

## callees

- `0x140001008`
- `0x14000efd0`
- `0x14000f7fc`
- `0x14004fdcc`
- `0x14004ffd0`
- `0x140050d78`
- `0x140051840`
- `0x140051df4`
- `0x140054c18`
- `0x140054fe8`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140079a24`
- `0x140079c48`
- `0x140079d0c`
- `0x140079da0`
- `0x14007ac74`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007b900`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140050ef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050f17`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005109e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400510c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005148b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400514db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050ef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050f17`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005109e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400510c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005148b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400514db`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051317`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051369`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051317`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051369`
- `ntoskrnl!PsGetHostSilo` at `0x140051141`
- `ntoskrnl!PsGetHostSilo` at `0x140051141`
- `ntoskrnl!ZwClose` at `0x140050f06`
- `ntoskrnl!ZwClose` at `0x1400510b2`
- `ntoskrnl!ZwClose` at `0x140050f06`
- `ntoskrnl!ZwClose` at `0x1400510b2`
- `ntoskrnl!ObfDereferenceObject` at `0x140051247`
- `ntoskrnl!ObfDereferenceObject` at `0x1400512a3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400514ad`
- `ntoskrnl!ObfDereferenceObject` at `0x140051501`
- `ntoskrnl!ObfDereferenceObject` at `0x140051590`
- `ntoskrnl!ObfDereferenceObject` at `0x1400515c8`
- `ntoskrnl!ObfDereferenceObject` at `0x140051247`
- `ntoskrnl!ObfDereferenceObject` at `0x1400512a3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400514ad`
- `ntoskrnl!ObfDereferenceObject` at `0x140051501`
- `ntoskrnl!ObfDereferenceObject` at `0x140051590`
- `ntoskrnl!ObfDereferenceObject` at `0x1400515c8`
- `FLTMGR!FltCreateFileEx2` at `0x140051210`
- `FLTMGR!FltCreateFileEx2` at `0x140051210`
- `FLTMGR!FltSetInformationFile` at `0x14005143a`
- `FLTMGR!FltSetInformationFile` at `0x14005143a`
- `FLTMGR!FltClose` at `0x14005116a`
- `FLTMGR!FltClose` at `0x1400512bc`
- `FLTMGR!FltClose` at `0x1400514c2`
- `FLTMGR!FltClose` at `0x140051516`
- `FLTMGR!FltClose` at `0x1400515dd`
- `FLTMGR!FltClose` at `0x14005116a`
- `FLTMGR!FltClose` at `0x1400512bc`
- `FLTMGR!FltClose` at `0x1400514c2`
- `FLTMGR!FltClose` at `0x140051516`
- `FLTMGR!FltClose` at `0x1400515dd`

## string_xrefs

- `0x140050ebb`: `PUSH: Allocating registry reader`
- `0x140050fbf`: `PUSH: Reading archive corrupt file reg key`
- `0x14005126f`: `API: Opening payload file to archive`
- `0x1400512e8`: `API: Computing name length`
- `0x1400513a5`: `ORIGIN: Allocating rename info buffer`
- `0x140051560`: `PUSH: Reopening payload file`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile(
        UnionFs::UfsPersistenceManager *this,
        struct UnionFs::UfsUnionCtx *a2,
        struct UnionFs::StackEventTracer *a3,
        char a4)
{
  UnionFs::UfsPersistenceManager *v7; // r15
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING *v9; // rdx
  int v10; // esi
  HANDLE *v11; // rbx
  HANDLE v12; // rcx
  const struct _UNICODE_STRING *v13; // rdx
  __int64 v14; // r8
  __int16 v15; // ax
  unsigned __int16 v16; // ax
  __int64 v17; // rcx
  __int64 v18; // rdx
  bool v19; // zf
  bool v20; // si
  HANDLE v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  struct _FILE_OBJECT *v25; // r14
  unsigned __int64 *v26; // rdx
  __int64 *v27; // rax
  volatile signed __int32 *v28; // rsi
  __int64 v29; // rbx
  void *v30; // rax
  const char *v31; // rax
  __int64 v32; // r8
  PVOID v33; // rcx
  PVOID v34; // rcx
  __int64 Length; // rdx
  __int64 v36; // r8
  struct _UNICODE_STRING *v37; // rdx
  ULONG v38; // r15d
  _DWORD *v39; // rbx
  unsigned __int64 *v40; // rdx
  __int64 *v41; // rax
  volatile signed __int32 *v42; // rsi
  __int64 v43; // r12
  NTSTATUS v44; // r14d
  struct _UNICODE_STRING *v45; // rdx
  PVOID v46; // rcx
  struct _UNICODE_STRING *v47; // rdx
  PVOID v48; // rcx
  PVOID v49; // rcx
  PVOID v50; // rcx
  int DesiredAccess; // [rsp+20h] [rbp-E0h]
  const char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  bool v54; // [rsp+80h] [rbp-80h] BYREF
  PVOID Object; // [rsp+88h] [rbp-78h] BYREF
  PVOID P; // [rsp+90h] [rbp-70h] BYREF
  PVOID FileInformation; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+A0h] [rbp-60h] BYREF
  char v59; // [rsp+B0h] [rbp-50h]
  PVOID FileHandle[2]; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING Source; // [rsp+C8h] [rbp-38h] BYREF
  UnionFs::UfsPersistenceManager *v62; // [rsp+D8h] [rbp-28h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+E0h] [rbp-20h] BYREF
  __int64 HostSilo; // [rsp+100h] [rbp+0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+108h] [rbp+8h] BYREF
  struct _OBJECT_ATTRIBUTES v66; // [rsp+120h] [rbp+20h] BYREF
  bool *v67; // [rsp+150h] [rbp+50h]
  __int64 v68; // [rsp+158h] [rbp+58h]
  PVOID *p_FileInformation; // [rsp+160h] [rbp+60h]
  __int64 v70; // [rsp+168h] [rbp+68h]
  HANDLE *p_RootDirectory; // [rsp+190h] [rbp+90h]

  v62 = this;
  v7 = this;
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x8000) != 0
    && (qword_14009E190 & 0x8000) == qword_14009E190 )
  {
    LODWORD(Object) = 339;
    P = "onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
    *(_QWORD *)&Destination.Length = "UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile";
    FileInformation = "ENTER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)byte_1400981F9,
      (_DWORD)a3,
      a4,
      (__int64)&FileInformation,
      (__int64)&Destination,
      (__int64)&P,
      (__int64)&Object);
  }
  LOBYTE(DesiredAccess) = 0;
  Source = 0;
  appended = UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName(v7, a2, &Source, a3, DesiredAccess);
  if ( appended < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)appended,
      (int)a3,
      (struct UnionFs::StackEventTracer *)0x850017015ELL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile",
      "PUSH: Getting payload file name",
      ObjectAttributes);
    goto LABEL_96;
  }
  v54 = 0;
  if ( !a4 )
    goto LABEL_87;
  P = 0;
  v10 = UnionFs::UfsRegistryReader::AllocAndInit((char *)UnionFs::g_FilterState + 8, &P, a3);
  if ( v10 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v10,
      (int)a3,
      (struct UnionFs::StackEventTracer *)0x7580017016CLL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile",
      "PUSH: Allocating registry reader",
      ObjectAttributes);
    v11 = (HANDLE *)P;
LABEL_10:
    if ( v11 )
    {
      v12 = v11[1];
      if ( v12 )
        ExFreePoolWithTag(v12, 0);
      if ( *v11 )
        ZwClose(*v11);
      ExFreePoolWithTag(v11, 0);
    }
    appended = v10;
    goto LABEL_96;
  }
  v66.RootDirectory = off_14007E740;
  p_RootDirectory = &v66.RootDirectory;
  UnionFs::StackEventTracer::SetIgnoreStatusCallback(a3, &v66);
  v11 = (HANDLE *)P;
  v10 = UnionFs::UfsRegistryReader::ReadValue((UnionFs::UfsRegistryReader *)P, v13, &v54, a3);
  v14 = 1;
  v15 = *((_WORD *)a3 + 245);
  if ( v15 )
  {
    v16 = v15 - 1;
    *((_WORD *)a3 + 245) = v16;
    v17 = 120 * (v16 + 1LL);
    v18 = *(_QWORD *)((char *)a3 + v17);
    *(_QWORD *)((char *)a3 + v17) = 0;
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18);
      v14 = 1;
    }
  }
  if ( v10 == -1073741766 )
    goto LABEL_25;
  if ( v10 < 0 )
  {
    if ( v10 != -1073741772 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v10,
        (int)a3,
        (struct UnionFs::StackEventTracer *)0x75900170178LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile",
        "PUSH: Reading archive corrupt file reg key",
        ObjectAttributes);
      goto LABEL_10;
    }
    goto LABEL_25;
  }
  v19 = v10 == -1073741772;
  v20 = v54;
  if ( v19 )
LABEL_25:
    v20 = 0;
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x400000000000LL) != 0
    && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
  {
    FileInformation = (PVOID)1;
    p_FileInformation = &FileInformation;
    v54 = v20;
    v67 = &v54;
    *(_QWORD *)&Destination.Length = 0x1000000;
    v66.SecurityDescriptor = &Destination;
    v70 = 8;
    v68 = 1;
    v66.SecurityQualityOfService = (PVOID)8;
    tlgWriteAgg((unsigned int)&dword_14009E178, (unsigned int)&word_14009833E, 0, 5, (__int64)&v66);
  }
  if ( v11 )
  {
    v21 = v11[1];
    if ( v21 )
      ExFreePoolWithTag(v21, 0);
    if ( *v11 )
      ZwClose(*v11);
    ExFreePoolWithTag(v11, 0);
  }
  if ( v20 )
  {
    v22 = (*(__int64 (__fastcall **)(UnionFs::UfsPersistenceManager *, struct UnionFs::UfsUnionCtx *, __int64))(*(_QWORD *)v7 + 96LL))(
            v7,
            a2,
            v14);
    P = 0;
    v25 = (struct _FILE_OBJECT *)v22;
    Object = 0;
    if ( v22 )
      goto LABEL_60;
    *(_QWORD *)&v66.Length = 48;
    v66.ObjectName = &Source;
    *(_QWORD *)&v66.Attributes = 576;
    v66.RootDirectory = 0;
    memset(&DriverContext, 0, sizeof(DriverContext));
    HostSilo = 1;
    *(_OWORD *)&v66.SecurityDescriptor = 0;
    DriverContext.Size = 40;
    IoStatusBlock = 0;
    HostSilo = PsGetHostSilo(v24, v23);
    *(_QWORD *)&Destination.Length = &Object;
    Destination.Buffer = 0;
    v59 = 1;
    if ( P )
      FltClose(P);
    P = 0;
    FsFltWil::AcquirePushLockShared(&FileInformation, (char *)a2 + 72);
    v27 = (__int64 *)*((_QWORD *)a2 + 6);
    v28 = (volatile signed __int32 *)v27[1];
    v29 = *v27;
    if ( v28 )
      _InterlockedIncrement(v28 + 2);
    if ( FileInformation )
      FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)FileInformation, v26);
    appended = FltCreateFileEx2(
                 *(PFLT_FILTER *)UnionFs::g_FilterState,
                 **(PFLT_INSTANCE **)(v29 + 8),
                 &P,
                 (PFILE_OBJECT *)&Destination.Buffer,
                 0x10000u,
                 &v66,
                 &IoStatusBlock,
                 0,
                 0,
                 7u,
                 1u,
                 0,
                 0,
                 0,
                 0,
                 &DriverContext);
    if ( v28 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v28);
    if ( v59 )
    {
      v30 = **(void ***)&Destination.Length;
      **(_QWORD **)&Destination.Length = Destination.Buffer;
      if ( v30 )
        ObfDereferenceObject(v30);
    }
    if ( appended != -1073741766 && appended != -1073741772 )
    {
      if ( appended < 0 )
      {
        v31 = "API: Opening payload file to archive";
        v32 = 0x86001701B2LL;
LABEL_53:
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)appended,
          (int)a3,
          (struct UnionFs::StackEventTracer *)v32,
          (unsigned __int64)"UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile",
          v31,
          ObjectAttributes);
LABEL_54:
        v33 = Object;
        Object = 0;
        if ( v33 )
          ObfDereferenceObject(v33);
        v34 = P;
LABEL_57:
        if ( v34 )
          FltClose(v34);
        goto LABEL_96;
      }
      v25 = (struct _FILE_OBJECT *)Object;
      if ( Object )
      {
LABEL_60:
        Length = Source.Length;
        if ( (unsigned __int16)(Source.Length + 8) < Source.Length )
        {
          v31 = "API: Computing name length";
          v32 = 0x750001701BFLL;
          appended = -1073741675;
          goto LABEL_53;
        }
        LOWORD(Length) = Source.Length + 8;
        FsFltWil::MakeUniqueUnicodeString(&Destination, Length, 1279685446);
        appended = RtlAppendUnicodeStringToString(&Destination, &Source);
        if ( appended < 0 )
        {
          v36 = 0x68D001701C5LL;
LABEL_64:
          UnionFs::ProcessTraceStatusFromApi(
            (UnionFs *)(unsigned int)appended,
            (int)a3,
            (struct UnionFs::StackEventTracer *)v36,
            (unsigned __int64)"UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile",
            "API: ",
            ObjectAttributes);
LABEL_65:
          FsFltWil::Details::FreeUnicodeString(&Destination, v37);
          goto LABEL_54;
        }
        appended = RtlAppendUnicodeStringToString(&Destination, &stru_14007EDD0);
        if ( appended < 0 )
        {
          v36 = 0x68E001701CALL;
          goto LABEL_64;
        }
        v38 = Destination.Length + 20;
        utl::make_unique_pool<enum gsl::byte [0],256,1836074581,0>(&FileInformation, v38);
        v39 = FileInformation;
        if ( !FileInformation )
        {
          appended = -1073741670;
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC000009ALL,
            (int)a3,
            (struct UnionFs::StackEventTracer *)0x693001701D6LL,
            (unsigned __int64)"UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile",
            "ORIGIN: Allocating rename info buffer",
            ObjectAttributes);
          goto LABEL_65;
        }
        *(_BYTE *)FileInformation = 1;
        v39[4] = Destination.Length;
        memmove(v39 + 5, Destination.Buffer, Destination.Length);
        FsFltWil::AcquirePushLockShared(&FileInformation, (char *)a2 + 72);
        v41 = (__int64 *)*((_QWORD *)a2 + 6);
        v42 = (volatile signed __int32 *)v41[1];
        v43 = *v41;
        if ( v42 )
          _InterlockedIncrement(v42 + 2);
        if ( FileInformation )
          FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)FileInformation, v40);
        v44 = FltSetInformationFile(**(PFLT_INSTANCE **)(v43 + 8), v25, v39, v38, FileRenameInformation);
        if ( v42 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v42);
        if ( v44 < 0 )
        {
          UnionFs::ProcessTraceStatusFromApi(
            (UnionFs *)(unsigned int)v44,
            (int)a3,
            (struct UnionFs::StackEventTracer *)0x694001701E5LL,
            (unsigned __int64)"UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile",
            "API: Archiving payload file",
            ObjectAttributes);
          ExFreePoolWithTag(v39, 0);
          FsFltWil::Details::FreeUnicodeString(&Destination, v45);
          v46 = Object;
          Object = 0;
          if ( v46 )
            ObfDereferenceObject(v46);
          if ( P )
            FltClose(P);
          appended = v44;
          goto LABEL_96;
        }
        ExFreePoolWithTag(v39, 0);
        FsFltWil::Details::FreeUnicodeString(&Destination, v47);
        v7 = v62;
      }
    }
    v48 = Object;
    Object = 0;
    if ( v48 )
      ObfDereferenceObject(v48);
    if ( P )
      FltClose(P);
  }
LABEL_87:
  (*(void (__fastcall **)(UnionFs::UfsPersistenceManager *, struct UnionFs::UfsUnionCtx *))(*(_QWORD *)v7 + 112LL))(
    v7,
    a2);
  *(_OWORD *)FileHandle = 0;
  appended = UnionFs::UfsPersistenceManager::OpenPersistentPayloadFile(v7, a2, FileHandle, a3, 0);
  if ( appended < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)appended,
      (int)a3,
      (struct UnionFs::StackEventTracer *)0x754001701FBLL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile",
      "PUSH: Reopening payload file",
      ObjectAttributes);
    v49 = FileHandle[1];
    FileHandle[1] = 0;
    if ( v49 )
      ObfDereferenceObject(v49);
    v34 = FileHandle[0];
    goto LABEL_57;
  }
  (*(void (__fastcall **)(UnionFs::UfsPersistenceManager *, struct UnionFs::UfsUnionCtx *, PVOID *))(*(_QWORD *)v7 + 104LL))(
    v7,
    a2,
    FileHandle);
  v50 = FileHandle[1];
  FileHandle[1] = 0;
  if ( v50 )
    ObfDereferenceObject(v50);
  if ( FileHandle[0] )
    FltClose(FileHandle[0]);
  appended = 0;
LABEL_96:
  FsFltWil::Details::FreeUnicodeString(&Source, v9);
  lambda_207c86a80a9c155124a2a44a821c01b6_::operator()();
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140050d78  mov     [rsp-8+arg_18], rbx
0x140050d7d  push    rbp
0x140050d7e  push    rsi
0x140050d7f  push    rdi
0x140050d80  push    r12
0x140050d82  push    r13
0x140050d84  push    r14
0x140050d86  push    r15
0x140050d88  lea     rbp, [rsp-0B0h]
0x140050d90  sub     rsp, 1B0h
0x140050d97  mov     rax, cs:__security_cookie
0x140050d9e  xor     rax, rsp
0x140050da1  mov     [rbp+0E0h+var_40], rax
0x140050da8  mov     eax, cs:dword_14009E178
0x140050dae  lea     r14, aUnionfsUfspers_8; "UnionFs::UfsPersistenceManager::ClearPe"...
0x140050db5  mov     [rbp+0E0h+var_108], rcx
0x140050db9  mov     sil, r9b
0x140050dbc  mov     rdi, r8
0x140050dbf  mov     r13, rdx
0x140050dc2  mov     r15, rcx
0x140050dc5  cmp     eax, 5
0x140050dc8  jbe     short loc_140050E3E
0x140050dca  mov     rcx, cs:qword_14009E190
0x140050dd1  mov     edx, 8000h
0x140050dd6  mov     rax, cs:qword_14009E188
0x140050ddd  test    rdx, rax
0x140050de0  jz      short loc_140050E3E
0x140050de2  mov     rax, rcx
0x140050de5  and     rax, rdx
0x140050de8  cmp     rax, rcx
0x140050deb  jnz     short loc_140050E3E
0x140050ded  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x140050df4  mov     dword ptr [rbp+0E0h+Object], 153h
0x140050dfb  mov     [rbp+0E0h+P], rax
0x140050dff  lea     rdx, byte_1400981F9
0x140050e06  lea     rax, aEnter; "ENTER"
0x140050e0d  mov     qword ptr [rbp+0E0h+Destination.Length], r14
0x140050e11  mov     [rbp+0E0h+FileInformation], rax
0x140050e15  lea     rax, [rbp+0E0h+Object]
0x140050e19  mov     [rsp+1E0h+AllocationSize], rax
0x140050e1e  lea     rax, [rbp+0E0h+P]
0x140050e22  mov     [rsp+1E0h+IoStatusBlock], rax
0x140050e27  lea     rax, [rbp+0E0h+Destination]
0x140050e2b  mov     [rsp+1E0h+ObjectAttributes], rax; char *
0x140050e30  lea     rax, [rbp+0E0h+FileInformation]
0x140050e34  mov     qword ptr [rsp+1E0h+DesiredAccess], rax
0x140050e39  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140050e3e  xorps   xmm0, xmm0
0x140050e41  lea     r8, [rbp+0E0h+Source]
0x140050e45  xor     r12d, r12d
0x140050e48  mov     r9, rdi
0x140050e4b  mov     rdx, r13
0x140050e4e  mov     byte ptr [rsp+1E0h+DesiredAccess], r12b
0x140050e53  mov     rcx, r15
0x140050e56  movups  xmmword ptr [rbp+0E0h+Source.Length], xmm0
0x140050e5a  call    ?GeneratePersistentPayloadFileName@UfsPersistenceManager@UnionFs@@IEBAJAEBVUfsUnionCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName(UnionFs::UfsUnionCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,bool)
0x140050e5f  mov     ebx, eax
0x140050e61  test    eax, eax
0x140050e63  jns     short loc_140050E8D
0x140050e65  lea     rax, aPushGettingPay_0; "PUSH: Getting payload file name"
0x140050e6c  mov     r9, r14; unsigned __int64
0x140050e6f  mov     r8, 850017015Eh; struct UnionFs::StackEventTracer *
0x140050e79  mov     qword ptr [rsp+1E0h+DesiredAccess], rax; char *
0x140050e7e  mov     rdx, rdi; int
0x140050e81  mov     ecx, ebx; this
0x140050e83  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140050e88  jmp     loc_1400515EC
0x140050e8d  mov     [rbp+0E0h+var_160], r12b
0x140050e91  test    sil, sil
0x140050e94  jz      loc_140051529
0x140050e9a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140050ea1  lea     rdx, [rbp+0E0h+P]
0x140050ea5  add     rcx, 8
0x140050ea9  mov     [rbp+0E0h+P], r12
0x140050ead  mov     r8, rdi
0x140050eb0  call    ?AllocAndInit@UfsRegistryReader@UnionFs@@SAJAEBU_UNICODE_STRING@@AEAV?$unique_ptr@VUfsRegistryReader@UnionFs@@U?$default_delete@VUfsRegistryReader@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsRegistryReader::AllocAndInit(_UNICODE_STRING const &,utl::unique_ptr<UnionFs::UfsRegistryReader,utl::default_delete<UnionFs::UfsRegistryReader>> &,UnionFs::StackEventTracer &)
0x140050eb5  mov     esi, eax
0x140050eb7  test    eax, eax
0x140050eb9  jns     short loc_140050F2A
0x140050ebb  lea     rax, aPushAllocating_18; "PUSH: Allocating registry reader"
0x140050ec2  mov     r9, r14; unsigned __int64
0x140050ec5  mov     r8, 7580017016Ch; struct UnionFs::StackEventTracer *
0x140050ecf  mov     qword ptr [rsp+1E0h+DesiredAccess], rax; char *
0x140050ed4  mov     rdx, rdi; int
0x140050ed7  mov     ecx, esi; this
0x140050ed9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140050ede  mov     rbx, [rbp+0E0h+P]
0x140050ee2  test    rbx, rbx
0x140050ee5  jz      short loc_140050F23
0x140050ee7  mov     rcx, [rbx+8]; P
0x140050eeb  test    rcx, rcx
0x140050eee  jz      short loc_140050EFE
0x140050ef0  xor     edx, edx; Tag
0x140050ef2  call    cs:__imp_ExFreePoolWithTag
0x140050ef9  nop     dword ptr [rax+rax+00h]
0x140050efe  mov     rcx, [rbx]; Handle
0x140050f01  test    rcx, rcx
0x140050f04  jz      short loc_140050F12
0x140050f06  call    cs:__imp_ZwClose
0x140050f0d  nop     dword ptr [rax+rax+00h]
0x140050f12  xor     edx, edx; Tag
0x140050f14  mov     rcx, rbx; P
0x140050f17  call    cs:__imp_ExFreePoolWithTag
0x140050f1e  nop     dword ptr [rax+rax+00h]
0x140050f23  mov     ebx, esi
0x140050f25  jmp     loc_1400515EC
0x140050f2a  lea     rax, off_14007E740
0x140050f31  mov     rcx, rdi
0x140050f34  mov     [rbp+0E0h+var_C0.RootDirectory], rax
0x140050f38  lea     rdx, [rbp+0E0h+var_C0]
0x140050f3c  lea     rax, [rbp+0E0h+var_C0.RootDirectory]
0x140050f40  mov     [rbp+0E0h+var_50], rax
0x140050f47  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x140050f4c  mov     rbx, [rbp+0E0h+P]
0x140050f50  lea     r8, [rbp+0E0h+var_160]; bool *
0x140050f54  mov     rcx, rbx; this
0x140050f57  mov     r9, rdi; struct UnionFs::StackEventTracer *
0x140050f5a  call    ?ReadValue@UfsRegistryReader@UnionFs@@QEAAJAEBU_UNICODE_STRING@@PEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsRegistryReader::ReadValue(_UNICODE_STRING const &,bool *,UnionFs::StackEventTracer &)
0x140050f5f  mov     esi, eax
0x140050f61  mov     r8d, 1
0x140050f67  movzx   eax, word ptr [rdi+1EAh]
0x140050f6e  test    ax, ax
0x140050f71  jz      short loc_140050FAA
0x140050f73  sub     ax, r8w
0x140050f77  movzx   ecx, ax
0x140050f7a  mov     [rdi+1EAh], cx
0x140050f81  add     rcx, r8
0x140050f84  imul    rcx, 78h ; 'x'
0x140050f88  mov     rdx, [rcx+rdi]
0x140050f8c  mov     [rcx+rdi], r12
0x140050f90  test    rdx, rdx
0x140050f93  jz      short loc_140050FAA
0x140050f95  mov     rax, [rdx]
0x140050f98  mov     rcx, rdx
0x140050f9b  mov     rax, [rax+18h]
0x140050f9f  call    _guard_dispatch_icall
0x140050fa4  mov     r8d, 1
0x140050faa  mov     eax, 0C0000034h
0x140050faf  cmp     esi, 0C000003Ah
0x140050fb5  jz      short loc_140050FEF
0x140050fb7  test    esi, esi
0x140050fb9  jns     short loc_140050FE7
0x140050fbb  cmp     esi, eax
0x140050fbd  jz      short loc_140050FEF
0x140050fbf  lea     rax, aPushReadingArc; "PUSH: Reading archive corrupt file reg "...
0x140050fc6  mov     r9, r14; unsigned __int64
0x140050fc9  mov     r8, 75900170178h; struct UnionFs::StackEventTracer *
0x140050fd3  mov     qword ptr [rsp+1E0h+DesiredAccess], rax; char *
0x140050fd8  mov     rdx, rdi; int
0x140050fdb  mov     ecx, esi; this
0x140050fdd  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140050fe2  jmp     loc_140050EE2
0x140050fe7  cmp     esi, eax
0x140050fe9  mov     sil, [rbp+0E0h+var_160]
0x140050fed  jnz     short loc_140050FF2
0x140050fef  mov     sil, r12b
0x140050ff2  mov     eax, cs:dword_14009E178
0x140050ff8  cmp     eax, 5
0x140050ffb  jbe     loc_14005108E
0x140051001  mov     rcx, cs:qword_14009E190
0x140051008  mov     rdx, 400000000000h
0x140051012  mov     rax, cs:qword_14009E188
0x140051019  test    rdx, rax
0x14005101c  jz      short loc_14005108E
0x14005101e  mov     rax, rcx
0x140051021  and     rax, rdx
0x140051024  cmp     rax, rcx
0x140051027  jnz     short loc_14005108E
0x140051029  lea     rax, [rbp+0E0h+FileInformation]
0x14005102d  mov     [rbp+0E0h+FileInformation], r8
0x140051031  mov     [rbp+0E0h+var_80], rax
0x140051035  lea     rdx, word_14009833E
0x14005103c  lea     rax, [rbp+0E0h+var_160]
0x140051040  mov     [rbp+0E0h+var_160], sil
0x140051044  mov     [rbp+0E0h+var_90], rax
0x140051048  lea     rcx, dword_14009E178
0x14005104f  lea     rax, [rbp+0E0h+Destination]
0x140051053  mov     qword ptr [rbp+0E0h+Destination.Length], 1000000h
0x14005105b  mov     [rbp+0E0h+var_C0.SecurityDescriptor], rax
0x14005105f  mov     r9d, 5
0x140051065  lea     rax, [rbp+0E0h+var_C0]
0x140051069  mov     [rbp+0E0h+var_78], 8
0x140051071  xor     r8d, r8d
0x140051074  mov     qword ptr [rsp+1E0h+DesiredAccess], rax
0x140051079  mov     [rbp+0E0h+var_88], 1
0x140051081  mov     [rbp+0E0h+var_C0.SecurityQualityOfService], 8
0x140051089  call    _tlgWriteAgg
0x14005108e  test    rbx, rbx
0x140051091  jz      short loc_1400510CF
0x140051093  mov     rcx, [rbx+8]; P
0x140051097  test    rcx, rcx
0x14005109a  jz      short loc_1400510AA
0x14005109c  xor     edx, edx; Tag
0x14005109e  call    cs:__imp_ExFreePoolWithTag
0x1400510a5  nop     dword ptr [rax+rax+00h]
0x1400510aa  mov     rcx, [rbx]; Handle
0x1400510ad  test    rcx, rcx
0x1400510b0  jz      short loc_1400510BE
0x1400510b2  call    cs:__imp_ZwClose
0x1400510b9  nop     dword ptr [rax+rax+00h]
0x1400510be  xor     edx, edx; Tag
0x1400510c0  mov     rcx, rbx; P
0x1400510c3  call    cs:__imp_ExFreePoolWithTag
0x1400510ca  nop     dword ptr [rax+rax+00h]
0x1400510cf  test    sil, sil
0x1400510d2  jz      loc_140051529
0x1400510d8  mov     rax, [r15]
0x1400510db  mov     rdx, r13
0x1400510de  mov     rcx, r15
0x1400510e1  mov     rax, [rax+60h]
0x1400510e5  call    _guard_dispatch_icall
0x1400510ea  mov     [rbp+0E0h+P], r12
0x1400510ee  mov     r14, rax
0x1400510f1  mov     [rbp+0E0h+Object], r12
0x1400510f5  test    rax, rax
0x1400510f8  jnz     loc_1400512DA
0x1400510fe  lea     rax, [rbp+0E0h+Source]
0x140051102  mov     qword ptr [rbp+0E0h+var_C0.Length], 30h ; '0'
0x14005110a  xorps   xmm1, xmm1
0x14005110d  mov     [rbp+0E0h+var_C0.ObjectName], rax
0x140051111  lea     eax, [r14+28h]
0x140051115  mov     qword ptr [rbp+0E0h+var_C0.Attributes], 240h
0x14005111d  xorps   xmm0, xmm0
0x140051120  mov     [rbp+0E0h+var_C0.RootDirectory], r12
0x140051124  lea     r14d, [rax-27h]
0x140051128  movups  xmmword ptr [rbp+0E0h+var_100.Size], xmm1
0x14005112c  mov     [rbp+0E0h+var_E0], r14
0x140051130  movdqu  xmmword ptr [rbp+0E0h+var_C0.SecurityDescriptor], xmm0
0x140051135  mov     [rbp+0E0h+var_100.Size], ax
0x140051139  movups  xmmword ptr [rbp+0E0h+var_D8], xmm0
0x14005113d  movups  xmmword ptr [rbp+0E0h+var_100.DeviceObjectHint], xmm1
0x140051141  call    cs:__imp_PsGetHostSilo
0x140051148  nop     dword ptr [rax+rax+00h]
0x14005114d  mov     rcx, [rbp+0E0h+P]; FileHandle
0x140051151  mov     [rbp+0E0h+var_E0], rax
0x140051155  lea     rax, [rbp+0E0h+Object]
0x140051159  mov     qword ptr [rbp+0E0h+Destination.Length], rax
0x14005115d  mov     [rbp+0E0h+Destination.Buffer], r12
0x140051161  mov     [rbp+0E0h+var_130], r14b
0x140051165  test    rcx, rcx
0x140051168  jz      short loc_140051176
0x14005116a  call    cs:__imp_FltClose
0x140051171  nop     dword ptr [rax+rax+00h]
0x140051176  lea     rdx, [r13+48h]
0x14005117a  mov     [rbp+0E0h+P], r12
0x14005117e  lea     rcx, [rbp+0E0h+FileInformation]
0x140051182  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140051187  mov     rax, [r13+30h]
0x14005118b  mov     rsi, [rax+8]
0x14005118f  mov     rbx, [rax]
0x140051192  test    rsi, rsi
0x140051195  jz      short loc_14005119B
0x140051197  lock inc dword ptr [rsi+8]
0x14005119b  mov     rcx, [rbp+0E0h+FileInformation]; this
0x14005119f  test    rcx, rcx
0x1400511a2  jz      short loc_1400511A9
0x1400511a4  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400511a9  mov     rdx, [rbx+8]
0x1400511ad  lea     rax, [rbp+0E0h+var_100]
0x1400511b1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400511b8  lea     r9, [rbp+0E0h+Destination.Buffer]; FileObject
0x1400511bc  mov     [rsp+1E0h+DriverContext], rax; DriverContext
0x1400511c1  lea     r8, [rbp+0E0h+P]; FileHandle
0x1400511c5  mov     [rsp+1E0h+Flags], r12d; Flags
0x1400511ca  lea     rax, [rbp+0E0h+var_D8]
0x1400511ce  mov     rdx, [rdx]; Instance
0x1400511d1  mov     rcx, [rcx]; Filter
0x1400511d4  mov     [rsp+1E0h+EaLength], r12d; EaLength
0x1400511d9  mov     [rsp+1E0h+EaBuffer], r12; EaBuffer
0x1400511de  mov     [rsp+1E0h+CreateOptions], r12d; CreateOptions
0x1400511e3  mov     [rsp+1E0h+CreateDisposition], r14d; CreateDisposition
0x1400511e8  mov     [rsp+1E0h+ShareAccess], 7; ShareAccess
0x1400511f0  mov     [rsp+1E0h+FileAttributes], r12d; FileAttributes
0x1400511f5  mov     [rsp+1E0h+AllocationSize], r12; AllocationSize
0x1400511fa  mov     [rsp+1E0h+IoStatusBlock], rax; IoStatusBlock
0x1400511ff  lea     rax, [rbp+0E0h+var_C0]
0x140051203  mov     [rsp+1E0h+ObjectAttributes], rax; char *
0x140051208  mov     [rsp+1E0h+DesiredAccess], 10000h; DesiredAccess
0x140051210  call    cs:__imp_FltCreateFileEx2
0x140051217  nop     dword ptr [rax+rax+00h]
0x14005121c  mov     ebx, eax
0x14005121e  test    rsi, rsi
0x140051221  jz      short loc_14005122B
0x140051223  mov     rcx, rsi; this
0x140051226  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14005122b  cmp     [rbp+0E0h+var_130], r12b
0x14005122f  jz      short loc_140051253
0x140051231  mov     rdx, qword ptr [rbp+0E0h+Destination.Length]
0x140051235  mov     rcx, [rbp+0E0h+Destination.Buffer]
0x140051239  mov     rax, [rdx]
0x14005123c  mov     [rdx], rcx
0x14005123f  test    rax, rax
0x140051242  jz      short loc_140051253
0x140051244  mov     rcx, rax; Object
0x140051247  call    cs:__imp_ObfDereferenceObject
0x14005124e  nop     dword ptr [rax+rax+00h]
0x140051253  cmp     ebx, 0C000003Ah
0x140051259  jz      loc_1400514F4
0x14005125f  cmp     ebx, 0C0000034h
0x140051265  jz      loc_1400514F4
  ... truncated ...
```
