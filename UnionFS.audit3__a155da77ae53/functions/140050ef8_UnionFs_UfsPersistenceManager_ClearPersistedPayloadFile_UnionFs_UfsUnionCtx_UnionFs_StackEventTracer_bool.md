# UnionFs::UfsPersistenceManager::ClearPersistedPayloadFile(UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &,bool)

- ea: `0x140050ef8`
- end: `0x1400517a7`
- name: `?ClearPersistedPayloadFile@UfsPersistenceManager@UnionFs@@QEBAJAEAVUfsUnionCtx@2@AEAVStackEventTracer@2@_N@Z`
- size: `2223`
- prototype: `int(UnionFs::UfsPersistenceManager *__hidden this, struct UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *, bool)`
- caller_count: `4`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140020540`
- `0x140053698`
- `0x14005c3d0`
- `0x140062fd4`

## callees

- `0x140001008`
- `0x14000efa0`
- `0x14000f81c`
- `0x14004ff4c`
- `0x140050150`
- `0x140050ef8`
- `0x1400519c0`
- `0x140051f74`
- `0x140054d9c`
- `0x14005516c`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140079d44`
- `0x140079f68`
- `0x14007a02c`
- `0x14007a0c0`
- `0x14007af94`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bc40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140051072`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051097`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005121e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051243`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005160b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005165b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051072`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051097`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005121e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051243`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005160b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005165b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051497`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400514e9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051497`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400514e9`
- `ntoskrnl!PsGetHostSilo` at `0x1400512c1`
- `ntoskrnl!PsGetHostSilo` at `0x1400512c1`
- `ntoskrnl!ZwClose` at `0x140051086`
- `ntoskrnl!ZwClose` at `0x140051232`
- `ntoskrnl!ZwClose` at `0x140051086`
- `ntoskrnl!ZwClose` at `0x140051232`
- `ntoskrnl!ObfDereferenceObject` at `0x1400513c7`
- `ntoskrnl!ObfDereferenceObject` at `0x140051423`
- `ntoskrnl!ObfDereferenceObject` at `0x14005162d`
- `ntoskrnl!ObfDereferenceObject` at `0x140051681`
- `ntoskrnl!ObfDereferenceObject` at `0x140051710`
- `ntoskrnl!ObfDereferenceObject` at `0x140051748`
- `ntoskrnl!ObfDereferenceObject` at `0x1400513c7`
- `ntoskrnl!ObfDereferenceObject` at `0x140051423`
- `ntoskrnl!ObfDereferenceObject` at `0x14005162d`
- `ntoskrnl!ObfDereferenceObject` at `0x140051681`
- `ntoskrnl!ObfDereferenceObject` at `0x140051710`
- `ntoskrnl!ObfDereferenceObject` at `0x140051748`
- `FLTMGR!FltCreateFileEx2` at `0x140051390`
- `FLTMGR!FltCreateFileEx2` at `0x140051390`
- `FLTMGR!FltSetInformationFile` at `0x1400515ba`
- `FLTMGR!FltSetInformationFile` at `0x1400515ba`
- `FLTMGR!FltClose` at `0x1400512ea`
- `FLTMGR!FltClose` at `0x14005143c`
- `FLTMGR!FltClose` at `0x140051642`
- `FLTMGR!FltClose` at `0x140051696`
- `FLTMGR!FltClose` at `0x14005175d`
- `FLTMGR!FltClose` at `0x1400512ea`
- `FLTMGR!FltClose` at `0x14005143c`
- `FLTMGR!FltClose` at `0x140051642`
- `FLTMGR!FltClose` at `0x140051696`
- `FLTMGR!FltClose` at `0x14005175d`

## string_xrefs

- `0x14005103b`: `PUSH: Allocating registry reader`
- `0x14005113f`: `PUSH: Reading archive corrupt file reg key`
- `0x1400513ef`: `API: Opening payload file to archive`
- `0x140051468`: `API: Computing name length`
- `0x140051525`: `ORIGIN: Allocating rename info buffer`
- `0x1400516e0`: `PUSH: Reopening payload file`

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
      (unsigned int)byte_140098279,
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
  v66.RootDirectory = off_14007E748;
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
    tlgWriteAgg((unsigned int)&dword_14009E178, (unsigned int)&word_1400983BE, 0, 5, (__int64)&v66);
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
        appended = RtlAppendUnicodeStringToString(&Destination, &stru_14007EDD8);
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
0x140050ef8  mov     [rsp-8+arg_18], rbx
0x140050efd  push    rbp
0x140050efe  push    rsi
0x140050eff  push    rdi
0x140050f00  push    r12
0x140050f02  push    r13
0x140050f04  push    r14
0x140050f06  push    r15
0x140050f08  lea     rbp, [rsp-0B0h]
0x140050f10  sub     rsp, 1B0h
0x140050f17  mov     rax, cs:__security_cookie
0x140050f1e  xor     rax, rsp
0x140050f21  mov     [rbp+0E0h+var_40], rax
0x140050f28  mov     eax, cs:dword_14009E178
0x140050f2e  lea     r14, aUnionfsUfspers_8; "UnionFs::UfsPersistenceManager::ClearPe"...
0x140050f35  mov     [rbp+0E0h+var_108], rcx
0x140050f39  mov     sil, r9b
0x140050f3c  mov     rdi, r8
0x140050f3f  mov     r13, rdx
0x140050f42  mov     r15, rcx
0x140050f45  cmp     eax, 5
0x140050f48  jbe     short loc_140050FBE
0x140050f4a  mov     rcx, cs:qword_14009E190
0x140050f51  mov     edx, 8000h
0x140050f56  mov     rax, cs:qword_14009E188
0x140050f5d  test    rdx, rax
0x140050f60  jz      short loc_140050FBE
0x140050f62  mov     rax, rcx
0x140050f65  and     rax, rdx
0x140050f68  cmp     rax, rcx
0x140050f6b  jnz     short loc_140050FBE
0x140050f6d  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x140050f74  mov     dword ptr [rbp+0E0h+Object], 153h
0x140050f7b  mov     [rbp+0E0h+P], rax
0x140050f7f  lea     rdx, byte_140098279
0x140050f86  lea     rax, aEnter; "ENTER"
0x140050f8d  mov     qword ptr [rbp+0E0h+Destination.Length], r14
0x140050f91  mov     [rbp+0E0h+FileInformation], rax
0x140050f95  lea     rax, [rbp+0E0h+Object]
0x140050f99  mov     [rsp+1E0h+AllocationSize], rax
0x140050f9e  lea     rax, [rbp+0E0h+P]
0x140050fa2  mov     [rsp+1E0h+IoStatusBlock], rax
0x140050fa7  lea     rax, [rbp+0E0h+Destination]
0x140050fab  mov     [rsp+1E0h+ObjectAttributes], rax; char *
0x140050fb0  lea     rax, [rbp+0E0h+FileInformation]
0x140050fb4  mov     qword ptr [rsp+1E0h+DesiredAccess], rax
0x140050fb9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140050fbe  xorps   xmm0, xmm0
0x140050fc1  lea     r8, [rbp+0E0h+Source]
0x140050fc5  xor     r12d, r12d
0x140050fc8  mov     r9, rdi
0x140050fcb  mov     rdx, r13
0x140050fce  mov     byte ptr [rsp+1E0h+DesiredAccess], r12b
0x140050fd3  mov     rcx, r15
0x140050fd6  movups  xmmword ptr [rbp+0E0h+Source.Length], xmm0
0x140050fda  call    ?GeneratePersistentPayloadFileName@UfsPersistenceManager@UnionFs@@IEBAJAEBVUfsUnionCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@_N@Z; UnionFs::UfsPersistenceManager::GeneratePersistentPayloadFileName(UnionFs::UfsUnionCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &,bool)
0x140050fdf  mov     ebx, eax
0x140050fe1  test    eax, eax
0x140050fe3  jns     short loc_14005100D
0x140050fe5  lea     rax, aPushGettingPay_0; "PUSH: Getting payload file name"
0x140050fec  mov     r9, r14; unsigned __int64
0x140050fef  mov     r8, 850017015Eh; struct UnionFs::StackEventTracer *
0x140050ff9  mov     qword ptr [rsp+1E0h+DesiredAccess], rax; char *
0x140050ffe  mov     rdx, rdi; int
0x140051001  mov     ecx, ebx; this
0x140051003  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140051008  jmp     loc_14005176C
0x14005100d  mov     [rbp+0E0h+var_160], r12b
0x140051011  test    sil, sil
0x140051014  jz      loc_1400516A9
0x14005101a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140051021  lea     rdx, [rbp+0E0h+P]
0x140051025  add     rcx, 8
0x140051029  mov     [rbp+0E0h+P], r12
0x14005102d  mov     r8, rdi
0x140051030  call    ?AllocAndInit@UfsRegistryReader@UnionFs@@SAJAEBU_UNICODE_STRING@@AEAV?$unique_ptr@VUfsRegistryReader@UnionFs@@U?$default_delete@VUfsRegistryReader@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsRegistryReader::AllocAndInit(_UNICODE_STRING const &,utl::unique_ptr<UnionFs::UfsRegistryReader,utl::default_delete<UnionFs::UfsRegistryReader>> &,UnionFs::StackEventTracer &)
0x140051035  mov     esi, eax
0x140051037  test    eax, eax
0x140051039  jns     short loc_1400510AA
0x14005103b  lea     rax, aPushAllocating_18; "PUSH: Allocating registry reader"
0x140051042  mov     r9, r14; unsigned __int64
0x140051045  mov     r8, 7580017016Ch; struct UnionFs::StackEventTracer *
0x14005104f  mov     qword ptr [rsp+1E0h+DesiredAccess], rax; char *
0x140051054  mov     rdx, rdi; int
0x140051057  mov     ecx, esi; this
0x140051059  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005105e  mov     rbx, [rbp+0E0h+P]
0x140051062  test    rbx, rbx
0x140051065  jz      short loc_1400510A3
0x140051067  mov     rcx, [rbx+8]; P
0x14005106b  test    rcx, rcx
0x14005106e  jz      short loc_14005107E
0x140051070  xor     edx, edx; Tag
0x140051072  call    cs:__imp_ExFreePoolWithTag
0x140051079  nop     dword ptr [rax+rax+00h]
0x14005107e  mov     rcx, [rbx]; Handle
0x140051081  test    rcx, rcx
0x140051084  jz      short loc_140051092
0x140051086  call    cs:__imp_ZwClose
0x14005108d  nop     dword ptr [rax+rax+00h]
0x140051092  xor     edx, edx; Tag
0x140051094  mov     rcx, rbx; P
0x140051097  call    cs:__imp_ExFreePoolWithTag
0x14005109e  nop     dword ptr [rax+rax+00h]
0x1400510a3  mov     ebx, esi
0x1400510a5  jmp     loc_14005176C
0x1400510aa  lea     rax, off_14007E748
0x1400510b1  mov     rcx, rdi
0x1400510b4  mov     [rbp+0E0h+var_C0.RootDirectory], rax
0x1400510b8  lea     rdx, [rbp+0E0h+var_C0]
0x1400510bc  lea     rax, [rbp+0E0h+var_C0.RootDirectory]
0x1400510c0  mov     [rbp+0E0h+var_50], rax
0x1400510c7  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x1400510cc  mov     rbx, [rbp+0E0h+P]
0x1400510d0  lea     r8, [rbp+0E0h+var_160]; bool *
0x1400510d4  mov     rcx, rbx; this
0x1400510d7  mov     r9, rdi; struct UnionFs::StackEventTracer *
0x1400510da  call    ?ReadValue@UfsRegistryReader@UnionFs@@QEAAJAEBU_UNICODE_STRING@@PEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsRegistryReader::ReadValue(_UNICODE_STRING const &,bool *,UnionFs::StackEventTracer &)
0x1400510df  mov     esi, eax
0x1400510e1  mov     r8d, 1
0x1400510e7  movzx   eax, word ptr [rdi+1EAh]
0x1400510ee  test    ax, ax
0x1400510f1  jz      short loc_14005112A
0x1400510f3  sub     ax, r8w
0x1400510f7  movzx   ecx, ax
0x1400510fa  mov     [rdi+1EAh], cx
0x140051101  add     rcx, r8
0x140051104  imul    rcx, 78h ; 'x'
0x140051108  mov     rdx, [rcx+rdi]
0x14005110c  mov     [rcx+rdi], r12
0x140051110  test    rdx, rdx
0x140051113  jz      short loc_14005112A
0x140051115  mov     rax, [rdx]
0x140051118  mov     rcx, rdx
0x14005111b  mov     rax, [rax+18h]
0x14005111f  call    _guard_dispatch_icall
0x140051124  mov     r8d, 1
0x14005112a  mov     eax, 0C0000034h
0x14005112f  cmp     esi, 0C000003Ah
0x140051135  jz      short loc_14005116F
0x140051137  test    esi, esi
0x140051139  jns     short loc_140051167
0x14005113b  cmp     esi, eax
0x14005113d  jz      short loc_14005116F
0x14005113f  lea     rax, aPushReadingArc; "PUSH: Reading archive corrupt file reg "...
0x140051146  mov     r9, r14; unsigned __int64
0x140051149  mov     r8, 75900170178h; struct UnionFs::StackEventTracer *
0x140051153  mov     qword ptr [rsp+1E0h+DesiredAccess], rax; char *
0x140051158  mov     rdx, rdi; int
0x14005115b  mov     ecx, esi; this
0x14005115d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140051162  jmp     loc_140051062
0x140051167  cmp     esi, eax
0x140051169  mov     sil, [rbp+0E0h+var_160]
0x14005116d  jnz     short loc_140051172
0x14005116f  mov     sil, r12b
0x140051172  mov     eax, cs:dword_14009E178
0x140051178  cmp     eax, 5
0x14005117b  jbe     loc_14005120E
0x140051181  mov     rcx, cs:qword_14009E190
0x140051188  mov     rdx, 400000000000h
0x140051192  mov     rax, cs:qword_14009E188
0x140051199  test    rdx, rax
0x14005119c  jz      short loc_14005120E
0x14005119e  mov     rax, rcx
0x1400511a1  and     rax, rdx
0x1400511a4  cmp     rax, rcx
0x1400511a7  jnz     short loc_14005120E
0x1400511a9  lea     rax, [rbp+0E0h+FileInformation]
0x1400511ad  mov     [rbp+0E0h+FileInformation], r8
0x1400511b1  mov     [rbp+0E0h+var_80], rax
0x1400511b5  lea     rdx, word_1400983BE
0x1400511bc  lea     rax, [rbp+0E0h+var_160]
0x1400511c0  mov     [rbp+0E0h+var_160], sil
0x1400511c4  mov     [rbp+0E0h+var_90], rax
0x1400511c8  lea     rcx, dword_14009E178
0x1400511cf  lea     rax, [rbp+0E0h+Destination]
0x1400511d3  mov     qword ptr [rbp+0E0h+Destination.Length], 1000000h
0x1400511db  mov     [rbp+0E0h+var_C0.SecurityDescriptor], rax
0x1400511df  mov     r9d, 5
0x1400511e5  lea     rax, [rbp+0E0h+var_C0]
0x1400511e9  mov     [rbp+0E0h+var_78], 8
0x1400511f1  xor     r8d, r8d
0x1400511f4  mov     qword ptr [rsp+1E0h+DesiredAccess], rax
0x1400511f9  mov     [rbp+0E0h+var_88], 1
0x140051201  mov     [rbp+0E0h+var_C0.SecurityQualityOfService], 8
0x140051209  call    _tlgWriteAgg
0x14005120e  test    rbx, rbx
0x140051211  jz      short loc_14005124F
0x140051213  mov     rcx, [rbx+8]; P
0x140051217  test    rcx, rcx
0x14005121a  jz      short loc_14005122A
0x14005121c  xor     edx, edx; Tag
0x14005121e  call    cs:__imp_ExFreePoolWithTag
0x140051225  nop     dword ptr [rax+rax+00h]
0x14005122a  mov     rcx, [rbx]; Handle
0x14005122d  test    rcx, rcx
0x140051230  jz      short loc_14005123E
0x140051232  call    cs:__imp_ZwClose
0x140051239  nop     dword ptr [rax+rax+00h]
0x14005123e  xor     edx, edx; Tag
0x140051240  mov     rcx, rbx; P
0x140051243  call    cs:__imp_ExFreePoolWithTag
0x14005124a  nop     dword ptr [rax+rax+00h]
0x14005124f  test    sil, sil
0x140051252  jz      loc_1400516A9
0x140051258  mov     rax, [r15]
0x14005125b  mov     rdx, r13
0x14005125e  mov     rcx, r15
0x140051261  mov     rax, [rax+60h]
0x140051265  call    _guard_dispatch_icall
0x14005126a  mov     [rbp+0E0h+P], r12
0x14005126e  mov     r14, rax
0x140051271  mov     [rbp+0E0h+Object], r12
0x140051275  test    rax, rax
0x140051278  jnz     loc_14005145A
0x14005127e  lea     rax, [rbp+0E0h+Source]
0x140051282  mov     qword ptr [rbp+0E0h+var_C0.Length], 30h ; '0'
0x14005128a  xorps   xmm1, xmm1
0x14005128d  mov     [rbp+0E0h+var_C0.ObjectName], rax
0x140051291  lea     eax, [r14+28h]
0x140051295  mov     qword ptr [rbp+0E0h+var_C0.Attributes], 240h
0x14005129d  xorps   xmm0, xmm0
0x1400512a0  mov     [rbp+0E0h+var_C0.RootDirectory], r12
0x1400512a4  lea     r14d, [rax-27h]
0x1400512a8  movups  xmmword ptr [rbp+0E0h+var_100.Size], xmm1
0x1400512ac  mov     [rbp+0E0h+var_E0], r14
0x1400512b0  movdqu  xmmword ptr [rbp+0E0h+var_C0.SecurityDescriptor], xmm0
0x1400512b5  mov     [rbp+0E0h+var_100.Size], ax
0x1400512b9  movups  xmmword ptr [rbp+0E0h+var_D8], xmm0
0x1400512bd  movups  xmmword ptr [rbp+0E0h+var_100.DeviceObjectHint], xmm1
0x1400512c1  call    cs:__imp_PsGetHostSilo
0x1400512c8  nop     dword ptr [rax+rax+00h]
0x1400512cd  mov     rcx, [rbp+0E0h+P]; FileHandle
0x1400512d1  mov     [rbp+0E0h+var_E0], rax
0x1400512d5  lea     rax, [rbp+0E0h+Object]
0x1400512d9  mov     qword ptr [rbp+0E0h+Destination.Length], rax
0x1400512dd  mov     [rbp+0E0h+Destination.Buffer], r12
0x1400512e1  mov     [rbp+0E0h+var_130], r14b
0x1400512e5  test    rcx, rcx
0x1400512e8  jz      short loc_1400512F6
0x1400512ea  call    cs:__imp_FltClose
0x1400512f1  nop     dword ptr [rax+rax+00h]
0x1400512f6  lea     rdx, [r13+48h]
0x1400512fa  mov     [rbp+0E0h+P], r12
0x1400512fe  lea     rcx, [rbp+0E0h+FileInformation]
0x140051302  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140051307  mov     rax, [r13+30h]
0x14005130b  mov     rsi, [rax+8]
0x14005130f  mov     rbx, [rax]
0x140051312  test    rsi, rsi
0x140051315  jz      short loc_14005131B
0x140051317  lock inc dword ptr [rsi+8]
0x14005131b  mov     rcx, [rbp+0E0h+FileInformation]; this
0x14005131f  test    rcx, rcx
0x140051322  jz      short loc_140051329
0x140051324  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140051329  mov     rdx, [rbx+8]
0x14005132d  lea     rax, [rbp+0E0h+var_100]
0x140051331  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140051338  lea     r9, [rbp+0E0h+Destination.Buffer]; FileObject
0x14005133c  mov     [rsp+1E0h+DriverContext], rax; DriverContext
0x140051341  lea     r8, [rbp+0E0h+P]; FileHandle
0x140051345  mov     [rsp+1E0h+Flags], r12d; Flags
0x14005134a  lea     rax, [rbp+0E0h+var_D8]
0x14005134e  mov     rdx, [rdx]; Instance
0x140051351  mov     rcx, [rcx]; Filter
0x140051354  mov     [rsp+1E0h+EaLength], r12d; EaLength
0x140051359  mov     [rsp+1E0h+EaBuffer], r12; EaBuffer
0x14005135e  mov     [rsp+1E0h+CreateOptions], r12d; CreateOptions
0x140051363  mov     [rsp+1E0h+CreateDisposition], r14d; CreateDisposition
0x140051368  mov     [rsp+1E0h+ShareAccess], 7; ShareAccess
0x140051370  mov     [rsp+1E0h+FileAttributes], r12d; FileAttributes
0x140051375  mov     [rsp+1E0h+AllocationSize], r12; AllocationSize
0x14005137a  mov     [rsp+1E0h+IoStatusBlock], rax; IoStatusBlock
0x14005137f  lea     rax, [rbp+0E0h+var_C0]
0x140051383  mov     [rsp+1E0h+ObjectAttributes], rax; char *
0x140051388  mov     [rsp+1E0h+DesiredAccess], 10000h; DesiredAccess
0x140051390  call    cs:__imp_FltCreateFileEx2
0x140051397  nop     dword ptr [rax+rax+00h]
0x14005139c  mov     ebx, eax
0x14005139e  test    rsi, rsi
0x1400513a1  jz      short loc_1400513AB
0x1400513a3  mov     rcx, rsi; this
0x1400513a6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400513ab  cmp     [rbp+0E0h+var_130], r12b
0x1400513af  jz      short loc_1400513D3
0x1400513b1  mov     rdx, qword ptr [rbp+0E0h+Destination.Length]
0x1400513b5  mov     rcx, [rbp+0E0h+Destination.Buffer]
0x1400513b9  mov     rax, [rdx]
0x1400513bc  mov     [rdx], rcx
0x1400513bf  test    rax, rax
0x1400513c2  jz      short loc_1400513D3
0x1400513c4  mov     rcx, rax; Object
0x1400513c7  call    cs:__imp_ObfDereferenceObject
0x1400513ce  nop     dword ptr [rax+rax+00h]
0x1400513d3  cmp     ebx, 0C000003Ah
0x1400513d9  jz      loc_140051674
0x1400513df  cmp     ebx, 0C0000034h
0x1400513e5  jz      loc_140051674
  ... truncated ...
```
