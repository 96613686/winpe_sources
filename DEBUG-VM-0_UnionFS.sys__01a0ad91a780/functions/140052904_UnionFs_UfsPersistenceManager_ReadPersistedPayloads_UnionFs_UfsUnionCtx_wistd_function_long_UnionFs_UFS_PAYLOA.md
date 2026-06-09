# UnionFs::UfsPersistenceManager::ReadPersistedPayloads(UnionFs::UfsUnionCtx &,wistd::function<long (UnionFs::UFS_PAYLOAD_INFORMATION const &,UnionFs::UFS_PAYLOAD_VERSION_HEADER const &,UnionFs::StackEventTracer &)>,ulong *,UnionFs::StackEventTracer &)

- ea: `0x140052904`
- end: `0x140053153`
- name: `?ReadPersistedPayloads@UfsPersistenceManager@UnionFs@@QEBAJAEAVUfsUnionCtx@2@V?$function@$$A6AJAEBUUFS_PAYLOAD_INFORMATION@UnionFs@@AEBUUFS_PAYLOAD_VERSION_HEADER@2@AEAVStackEventTracer@2@@Z@wistd@@PEAKAEAVStackEventTracer@2@@Z`
- size: `2127`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140020540`
- `0x14005c3d0`
- `0x140066af8`

## callees

- `0x140001008`
- `0x14000f81c`
- `0x14003dc14`
- `0x14004fee4`
- `0x140050804`
- `0x140051f74`
- `0x140052904`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140079d44`
- `0x14007a0c0`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140052f0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052f73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052fbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052f0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052f73`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052fbe`
- `ntoskrnl!ObfDereferenceObject` at `0x140052a59`
- `ntoskrnl!ObfDereferenceObject` at `0x140052aeb`
- `ntoskrnl!ObfDereferenceObject` at `0x140052a59`
- `ntoskrnl!ObfDereferenceObject` at `0x140052aeb`
- `FLTMGR!FltReadFile` at `0x140052cff`
- `FLTMGR!FltReadFile` at `0x140052cff`
- `FLTMGR!FltClose` at `0x140052a6e`
- `FLTMGR!FltClose` at `0x140052b00`
- `FLTMGR!FltClose` at `0x140052a6e`
- `FLTMGR!FltClose` at `0x140052b00`
- `FLTMGR!FltQueryInformationFile` at `0x140052b6f`
- `FLTMGR!FltQueryInformationFile` at `0x140052b6f`

## string_xrefs

- `0x140052a25`: `PUSH: Opening payload file`
- `0x14005295a`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052a8b`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052b9f`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052d79`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052f4c`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052f97`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052fe0`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140053093`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x1400530c9`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x1400530f7`: `UnionFs::UfsPersistenceManager::ReadPersistedPayloads`
- `0x140052a7a`: `PUSH: Opening file to read`
- `0x1400530b8`: `API: Reading chunks from payload file`
- `0x140052d84`: `Could not read entire payload chunk, may be old version or corrupt`
- `0x140052fcf`: `PUSH: Applying ReadPersistedPayloadsCallback`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPersistenceManager::ReadPersistedPayloads(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        __int64 a5)
{
  __int64 v7; // r13
  __int64 *v8; // r12
  __int64 v9; // r8
  const char *v10; // r9
  struct _FILE_OBJECT *v11; // r15
  NTSTATUS v12; // ebx
  PVOID v13; // rcx
  __int64 v14; // rcx
  void (*v15)(void); // rax
  __int64 v16; // rax
  PVOID v17; // rcx
  unsigned __int64 *v18; // rdx
  __int64 *v19; // rax
  volatile signed __int32 *v20; // rbx
  __int64 v21; // rdi
  NTSTATUS v22; // edi
  __int64 v23; // rcx
  __int64 v25; // r15
  unsigned __int64 *v26; // rdx
  __int64 *v27; // rax
  volatile signed __int32 *v28; // rbx
  __int64 v29; // rdi
  _QWORD *v30; // rdx
  __int64 *v31; // rdi
  ULONG v32; // eax
  char v33; // cl
  unsigned int v34; // r15d
  unsigned __int64 *v35; // rdx
  __int64 *v36; // rax
  volatile signed __int32 *v37; // r15
  __int64 v38; // rbx
  FsFltWil::Details *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  unsigned int *v42; // r13
  int v43; // eax
  __int64 v44; // rcx
  unsigned int v45; // ecx
  const char *v46; // rax
  __int64 v47; // r8
  __int64 v48; // rcx
  __int64 v49; // rcx
  const char *LengthReturned; // [rsp+28h] [rbp-B9h]
  const char *LengthReturneda; // [rsp+28h] [rbp-B9h]
  const char *LengthReturnedb; // [rsp+28h] [rbp-B9h]
  const char *LengthReturnedc; // [rsp+28h] [rbp-B9h]
  char v54; // [rsp+50h] [rbp-91h]
  ULONG Length; // [rsp+54h] [rbp-8Dh]
  PVOID Buffer; // [rsp+58h] [rbp-89h] BYREF
  ULONG BytesRead; // [rsp+60h] [rbp-81h] BYREF
  unsigned int v58; // [rsp+64h] [rbp-7Dh] BYREF
  PFILE_OBJECT FileObject; // [rsp+68h] [rbp-79h] BYREF
  PVOID Object[2]; // [rsp+70h] [rbp-71h] BYREF
  const char *v61; // [rsp+80h] [rbp-61h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+88h] [rbp-59h] BYREF
  __int64 v63; // [rsp+90h] [rbp-51h] BYREF
  __int64 *v64; // [rsp+98h] [rbp-49h]
  __int64 v65; // [rsp+A0h] [rbp-41h]
  const char *v66; // [rsp+A8h] [rbp-39h] BYREF
  char v67[8]; // [rsp+B0h] [rbp-31h] BYREF
  const char *v68; // [rsp+B8h] [rbp-29h] BYREF
  _DWORD *v69; // [rsp+C0h] [rbp-21h]
  __int64 v70; // [rsp+C8h] [rbp-19h]
  __int128 FileInformation; // [rsp+D0h] [rbp-11h] BYREF
  __int64 v72; // [rsp+E0h] [rbp-1h]

  v70 = a2;
  v7 = a2;
  v69 = a4;
  v8 = a1;
  v64 = a1;
  v9 = 0x8000;
  v10 = "onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x8000) != 0
    && (qword_14009E190 & 0x8000) == qword_14009E190 )
  {
    Buffer = (PVOID)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads";
    v61 = "ENTER";
    BytesRead = 173;
    FileObject = (PFILE_OBJECT)"onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)&dword_14009833C,
      0x8000,
      (unsigned int)"onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp",
      (__int64)&v61,
      (__int64)&Buffer,
      (__int64)&FileObject,
      (__int64)&BytesRead);
  }
  *a4 = 0;
  FileObject = (PFILE_OBJECT)(*(__int64 (__fastcall **)(__int64 *, __int64, __int64, const char *))(*v8 + 96))(
                               v8,
                               v7,
                               v9,
                               v10);
  v11 = FileObject;
  if ( !FileObject )
  {
    *(_OWORD *)Object = 0;
    v12 = UnionFs::UfsPersistenceManager::OpenPersistentPayloadFile(v8, v7, Object, a5, 3);
    if ( v12 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v12,
        a5,
        (struct UnionFs::StackEventTracer *)0x7B60017009DLL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::GetPayloadFileObject",
        "PUSH: Opening payload file",
        LengthReturned);
      v13 = Object[1];
      Object[1] = 0;
      if ( v13 )
        ObfDereferenceObject(v13);
      if ( Object[0] )
        FltClose(Object[0]);
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v12,
        a5,
        (struct UnionFs::StackEventTracer *)0x32B001700BBLL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
        "PUSH: Opening file to read",
        LengthReturneda);
LABEL_12:
      lambda_fd806375622af003ca3a1e8511b068d0_::operator()();
      v14 = *(_QWORD *)(a3 + 112);
      if ( v14 )
      {
        v15 = *(void (**)(void))(*(_QWORD *)v14 + 24LL);
        goto LABEL_92;
      }
      return (unsigned int)v12;
    }
    v16 = *v8;
    v11 = (struct _FILE_OBJECT *)Object[1];
    FileObject = (PFILE_OBJECT)Object[1];
    (*(void (__fastcall **)(__int64 *, __int64, PVOID *))(v16 + 104))(v8, v7, Object);
    v17 = Object[1];
    Object[1] = 0;
    if ( v17 )
      ObfDereferenceObject(v17);
    if ( Object[0] )
      FltClose(Object[0]);
  }
  FileInformation = 0;
  v72 = 0;
  FsFltWil::AcquirePushLockShared(&Buffer, v7 + 72);
  v19 = *(__int64 **)(v7 + 48);
  v20 = (volatile signed __int32 *)v19[1];
  v21 = *v19;
  if ( v20 )
    _InterlockedIncrement(v20 + 2);
  if ( Buffer )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Buffer, v18);
  v22 = FltQueryInformationFile(**(PFLT_INSTANCE **)(v21 + 8), v11, &FileInformation, 0x18u, FileStandardInformation, 0);
  if ( v20 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
  if ( v22 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v22,
      a5,
      (struct UnionFs::StackEventTracer *)0x2C5001700C8LL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
      "API: Querying standard info",
      LengthReturnedb);
    lambda_fd806375622af003ca3a1e8511b068d0_::operator()();
    v23 = *(_QWORD *)(a3 + 112);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
    return (unsigned int)v22;
  }
  if ( !*((_QWORD *)&FileInformation + 1) )
  {
LABEL_72:
    lambda_fd806375622af003ca3a1e8511b068d0_::operator()();
    v48 = *(_QWORD *)(a3 + 112);
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 24LL))(v48);
    return 0;
  }
  v25 = *(unsigned int *)(v7 + 300);
  Length = *(_DWORD *)(v7 + 300);
  ByteOffset.QuadPart = 0;
  FsFltWil::AcquirePushLockShared(&Buffer, v7 + 72);
  v27 = *(__int64 **)(v7 + 48);
  v28 = (volatile signed __int32 *)v27[1];
  v29 = *v27;
  if ( v28 )
    _InterlockedIncrement(v28 + 2);
  if ( Buffer )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Buffer, v26);
  v30 = *(_QWORD **)(v29 + 8);
  v65 = v25;
  utl::make_unique_aligned_pool<enum gsl::byte [0],1,1836074581,0>(&Buffer, *v30, v25);
  if ( v28 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v28);
  v31 = (__int64 *)Buffer;
  if ( !Buffer )
  {
    v12 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x4A4001700E2LL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
      "ORIGIN: Allocating payload info buffer",
      LengthReturnedb);
    goto LABEL_90;
  }
  v32 = Length;
  v33 = 1;
  v34 = 0;
  v54 = 1;
  v63 = 0;
  while ( 1 )
  {
    if ( !v33 )
    {
      if ( v34 != v32 )
        goto LABEL_57;
      ByteOffset.QuadPart += v65;
    }
    BytesRead = 0;
    FsFltWil::AcquirePushLockShared(&Buffer, v7 + 72);
    v36 = *(__int64 **)(v7 + 48);
    v37 = (volatile signed __int32 *)v36[1];
    v38 = *v36;
    if ( v37 )
      _InterlockedIncrement(v37 + 2);
    v39 = (FsFltWil::Details *)Buffer;
    Buffer = 0;
    if ( v39 )
      FsFltWil::Details::ReleasePushLockShared(v39, v35);
    v12 = FltReadFile(**(PFLT_INSTANCE **)(v38 + 8), FileObject, &ByteOffset, Length, v31, 0, &BytesRead, 0, 0);
    if ( v37 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v37);
    if ( v12 < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v12,
        a5,
        (struct UnionFs::StackEventTracer *)0x2BC00170104LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
        "API: Reading chunks from payload file",
        LengthReturnedb);
LABEL_76:
      if ( v31 )
        ExFreePoolWithTag(v31, 0);
      goto LABEL_12;
    }
    if ( BytesRead != Length
      && (unsigned int)dword_14009E178 > 3
      && (qword_14009E188 & 0x8000) != 0
      && (qword_14009E190 & 0x8000) == qword_14009E190 )
    {
      LODWORD(v61) = 266;
      v66 = "onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
      *(_QWORD *)v67 = "UnionFs::UfsPersistenceManager::ReadPersistedPayloads";
      v68 = "Could not read entire payload chunk, may be old version or corrupt";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        qword_14009E190,
        (unsigned int)byte_140098175,
        v40,
        v41,
        (__int64)&v68,
        (__int64)v67,
        (__int64)&v66,
        (__int64)&v61);
    }
    v34 = 0;
    if ( v54 )
    {
      v63 = *v31;
      if ( (*(unsigned __int8 (__fastcall **)(__int64 *, __int64 *))(*v8 + 152))(v8, &v63) )
        v34 = 8;
      else
        (*(void (__fastcall **)(__int64 *, __int64))(*v8 + 24))(v8, v7);
      v54 = 0;
    }
LABEL_57:
    if ( Length - v34 < 0x14 )
      break;
    v42 = (unsigned int *)((char *)v31 + v34);
    v58 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, unsigned int *, __int64))(*v64 + 128))(
            v64,
            v42,
            &v58,
            a5);
    if ( v12 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v12,
        a5,
        (struct UnionFs::StackEventTracer *)0x663001705B8LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ValidatePayloadInfo",
        "PUSH: Getting payload size",
        LengthReturnedb);
      goto LABEL_87;
    }
    if ( v58 > Length - v34 )
    {
      v46 = "ORIGIN: Entry size is greater than remaining chunk size";
      v47 = 0x69B001705BFLL;
      goto LABEL_86;
    }
    if ( *v42 && v58 > *v42 )
    {
      v46 = "ORIGIN: Entry size is greater than NextEntryOffset";
      v47 = 0x7E001705C8LL;
      goto LABEL_86;
    }
    v8 = v64;
    v43 = (*(__int64 (__fastcall **)(__int64 *, char *, __int64))(*v64 + 120))(v64, (char *)v31 + v34, a5);
    v12 = v43;
    if ( v43 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v43,
        a5,
        (struct UnionFs::StackEventTracer *)0x68B001705CELL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ValidatePayloadInfo",
        "PUSH: Validating payload info",
        LengthReturnedb);
      goto LABEL_87;
    }
    v44 = *(_QWORD *)(a3 + 112);
    if ( !v44 )
      wistd::__throw_bad_function_call(0);
    v12 = (*(__int64 (__fastcall **)(__int64, char *, __int64 *, __int64))(*(_QWORD *)v44 + 32LL))(
            v44,
            (char *)v31 + v34,
            &v63,
            a5);
    if ( v12 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v12,
        a5,
        (struct UnionFs::StackEventTracer *)0x22A00170139LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
        "PUSH: Applying ReadPersistedPayloadsCallback",
        LengthReturnedb);
      goto LABEL_76;
    }
    v45 = v34 + *v42;
    if ( v45 < v34 )
    {
      v12 = -1073741675;
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)0xC0000095LL,
        a5,
        (struct UnionFs::StackEventTracer *)0x49E0017013ELL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
        "API: Adding NextEntryOffset to bufferOffset",
        LengthReturnedb);
      goto LABEL_79;
    }
    v32 = Length;
    v34 += *v42;
    if ( v45 > Length )
    {
      v12 = -1073741566;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000102LL,
        a5,
        (struct UnionFs::StackEventTracer *)0x4AF00170145LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
        "ORIGIN: Payload record extends beyond buffer",
        LengthReturnedb);
      goto LABEL_76;
    }
    ++*v69;
    if ( !*v42 )
    {
      if ( v31 )
        ExFreePoolWithTag(v31, 0);
      goto LABEL_72;
    }
    v7 = v70;
    v33 = v54;
  }
  v46 = "ORIGIN: RemainingChunkSize less than the size of payload info";
  v47 = 0x4B9001705B1LL;
LABEL_86:
  v12 = -1073741566;
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC0000102LL,
    a5,
    (struct UnionFs::StackEventTracer *)v47,
    (unsigned __int64)"UnionFs::UfsPersistenceManager::ValidatePayloadInfo",
    v46,
    LengthReturnedb);
LABEL_87:
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v12,
    a5,
    (struct UnionFs::StackEventTracer *)0x69A00170134LL,
    (unsigned __int64)"UnionFs::UfsPersistenceManager::ReadPersistedPayloads",
    "PUSH: Validating payload info",
    LengthReturnedc);
LABEL_79:
  if ( v31 )
    ExFreePoolWithTag(v31, 0);
LABEL_90:
  lambda_fd806375622af003ca3a1e8511b068d0_::operator()();
  v49 = *(_QWORD *)(a3 + 112);
  if ( v49 )
  {
    v15 = *(void (**)(void))(*(_QWORD *)v49 + 24LL);
LABEL_92:
    v15();
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140052904  push    rbp
0x140052906  push    rbx
0x140052907  push    rsi
0x140052908  push    rdi
0x140052909  push    r12
0x14005290b  push    r13
0x14005290d  push    r14
0x14005290f  push    r15
0x140052911  lea     rbp, [rsp-17h]
0x140052916  sub     rsp, 0F8h
0x14005291d  mov     rax, cs:__security_cookie
0x140052924  xor     rax, rsp
0x140052927  mov     [rbp+4Fh+var_48], rax
0x14005292b  mov     eax, cs:dword_14009E178
0x140052931  mov     rbx, r9
0x140052934  mov     rsi, qword ptr [rbp+4Fh+arg_20]
0x140052938  mov     r14, r8
0x14005293b  mov     [rbp+4Fh+var_68], rdx
0x14005293f  mov     r13, rdx
0x140052942  mov     [rbp+4Fh+var_70], rbx
0x140052946  mov     r12, rcx
0x140052949  mov     [rbp+4Fh+var_98], rcx
0x14005294d  mov     r8d, 8000h
0x140052953  lea     r9, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x14005295a  lea     rdx, aUnionfsUfspers_5; "UnionFs::UfsPersistenceManager::ReadPer"...
0x140052961  cmp     eax, 5
0x140052964  jbe     short loc_1400529D2
0x140052966  mov     rcx, cs:qword_14009E190
0x14005296d  mov     rax, cs:qword_14009E188
0x140052974  test    r8, rax
0x140052977  jz      short loc_1400529D2
0x140052979  mov     rax, rcx
0x14005297c  and     rax, r8
0x14005297f  cmp     rax, rcx
0x140052982  jnz     short loc_1400529D2
0x140052984  lea     rax, aEnter; "ENTER"
0x14005298b  mov     [rsp+130h+Buffer], rdx
0x140052990  mov     [rbp+4Fh+var_B0], rax
0x140052994  lea     rdx, dword_14009833C
0x14005299b  lea     rax, [rsp+130h+var_D0]
0x1400529a0  mov     [rsp+130h+var_D0], 0ADh
0x1400529a8  mov     [rsp+130h+CallbackRoutine], rax
0x1400529ad  lea     rax, [rbp+4Fh+FileObject]
0x1400529b1  mov     [rsp+130h+BytesRead], rax
0x1400529b6  lea     rax, [rsp+130h+Buffer]
0x1400529bb  mov     [rsp+130h+LengthReturned], rax; char *
0x1400529c0  lea     rax, [rbp+4Fh+var_B0]
0x1400529c4  mov     qword ptr [rsp+130h+FileInformationClass], rax
0x1400529c9  mov     [rbp+4Fh+FileObject], r9
0x1400529cd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400529d2  xor     edi, edi
0x1400529d4  mov     rdx, r13
0x1400529d7  mov     [rbx], edi
0x1400529d9  mov     rcx, r12
0x1400529dc  mov     rax, [r12]
0x1400529e0  mov     rax, [rax+60h]
0x1400529e4  call    _guard_dispatch_icall
0x1400529e9  mov     [rbp+4Fh+FileObject], rax
0x1400529ed  mov     r15, rax
0x1400529f0  test    rax, rax
0x1400529f3  jnz     loc_140052B0C
0x1400529f9  xorps   xmm0, xmm0
0x1400529fc  mov     [rsp+130h+FileInformationClass], 3
0x140052a04  mov     r9, rsi
0x140052a07  lea     r8, [rbp+4Fh+Object]
0x140052a0b  mov     rdx, r13
0x140052a0e  mov     rcx, r12
0x140052a11  movdqu  xmmword ptr [rbp+4Fh+Object], xmm0
0x140052a16  call    ?OpenPersistentPayloadFile@UfsPersistenceManager@UnionFs@@IEBAJAEBVUfsUnionCtx@2@AEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?FltClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_ptr@U_FILE_OBJECT@@U?$function_deleter@P6A_JPEAX@Z$1?ObfDereferenceObject@@YA_J0@Z@wil@@@wistd@@@utl@@AEAVStackEventTracer@2@W4OpenOrCreateDisposition@Utils@2@@Z; UnionFs::UfsPersistenceManager::OpenPersistentPayloadFile(UnionFs::UfsUnionCtx const &,utl::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&FltClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wistd::unique_ptr<_FILE_OBJECT,wil::function_deleter<__int64 (*)(void *),&ObfDereferenceObject(void *)>>> &,UnionFs::StackEventTracer &,UnionFs::Utils::OpenOrCreateDisposition)
0x140052a1b  mov     ebx, eax
0x140052a1d  test    eax, eax
0x140052a1f  jns     loc_140052ABF
0x140052a25  lea     rax, aPushOpeningPay; "PUSH: Opening payload file"
0x140052a2c  mov     r8, 7B60017009Dh; struct UnionFs::StackEventTracer *
0x140052a36  lea     r9, aUnionfsUfspers_7; "UnionFs::UfsPersistenceManager::GetPayl"...
0x140052a3d  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140052a42  mov     rdx, rsi; int
0x140052a45  mov     ecx, ebx; this
0x140052a47  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140052a4c  mov     rcx, [rbp+4Fh+Object+8]; Object
0x140052a50  mov     [rbp+4Fh+Object+8], rdi
0x140052a54  test    rcx, rcx
0x140052a57  jz      short loc_140052A65
0x140052a59  call    cs:__imp_ObfDereferenceObject
0x140052a60  nop     dword ptr [rax+rax+00h]
0x140052a65  mov     rcx, [rbp+4Fh+Object]; FileHandle
0x140052a69  test    rcx, rcx
0x140052a6c  jz      short loc_140052A7A
0x140052a6e  call    cs:__imp_FltClose
0x140052a75  nop     dword ptr [rax+rax+00h]
0x140052a7a  lea     rax, aPushOpeningFil; "PUSH: Opening file to read"
0x140052a81  mov     r8, 32B001700BBh; struct UnionFs::StackEventTracer *
0x140052a8b  lea     r9, aUnionfsUfspers_5; "UnionFs::UfsPersistenceManager::ReadPer"...
0x140052a92  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140052a97  mov     rdx, rsi; int
0x140052a9a  mov     ecx, ebx; this
0x140052a9c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140052aa1  call    _lambda_fd806375622af003ca3a1e8511b068d0___operator__
0x140052aa6  mov     rcx, [r14+70h]
0x140052aaa  test    rcx, rcx
0x140052aad  jz      loc_14005312A
0x140052ab3  mov     rax, [rcx]
0x140052ab6  mov     rax, [rax+18h]
0x140052aba  jmp     loc_140053125
0x140052abf  mov     rax, [r12]
0x140052ac3  lea     r8, [rbp+4Fh+Object]
0x140052ac7  mov     r15, [rbp+4Fh+Object+8]
0x140052acb  mov     rdx, r13
0x140052ace  mov     rcx, r12
0x140052ad1  mov     [rbp+4Fh+FileObject], r15
0x140052ad5  mov     rax, [rax+68h]
0x140052ad9  call    _guard_dispatch_icall
0x140052ade  mov     rcx, [rbp+4Fh+Object+8]; Object
0x140052ae2  mov     [rbp+4Fh+Object+8], rdi
0x140052ae6  test    rcx, rcx
0x140052ae9  jz      short loc_140052AF7
0x140052aeb  call    cs:__imp_ObfDereferenceObject
0x140052af2  nop     dword ptr [rax+rax+00h]
0x140052af7  mov     rcx, [rbp+4Fh+Object]; FileHandle
0x140052afb  test    rcx, rcx
0x140052afe  jz      short loc_140052B0C
0x140052b00  call    cs:__imp_FltClose
0x140052b07  nop     dword ptr [rax+rax+00h]
0x140052b0c  xorps   xmm0, xmm0
0x140052b0f  lea     rdx, [r13+48h]
0x140052b13  xor     eax, eax
0x140052b15  lea     rcx, [rsp+130h+Buffer]
0x140052b1a  movups  [rbp+4Fh+FileInformation], xmm0
0x140052b1e  mov     [rbp+4Fh+var_50], rax
0x140052b22  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140052b27  mov     rax, [r13+30h]
0x140052b2b  mov     rbx, [rax+8]
0x140052b2f  mov     rdi, [rax]
0x140052b32  test    rbx, rbx
0x140052b35  jz      short loc_140052B3B
0x140052b37  lock inc dword ptr [rbx+8]
0x140052b3b  mov     rcx, [rsp+130h+Buffer]; this
0x140052b40  test    rcx, rcx
0x140052b43  jz      short loc_140052B4A
0x140052b45  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140052b4a  mov     rcx, [rdi+8]
0x140052b4e  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x140052b52  mov     [rsp+130h+LengthReturned], 0; char *
0x140052b5b  mov     r9d, 18h; Length
0x140052b61  mov     rdx, r15; FileObject
0x140052b64  mov     [rsp+130h+FileInformationClass], 5; FileInformationClass
0x140052b6c  mov     rcx, [rcx]; Instance
0x140052b6f  call    cs:__imp_FltQueryInformationFile
0x140052b76  nop     dword ptr [rax+rax+00h]
0x140052b7b  mov     edi, eax
0x140052b7d  test    rbx, rbx
0x140052b80  jz      short loc_140052B8A
0x140052b82  mov     rcx, rbx; this
0x140052b85  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140052b8a  test    edi, edi
0x140052b8c  jns     short loc_140052BD6
0x140052b8e  lea     rax, aApiQueryingSta; "API: Querying standard info"
0x140052b95  mov     r8, 2C5001700C8h; struct UnionFs::StackEventTracer *
0x140052b9f  lea     r9, aUnionfsUfspers_5; "UnionFs::UfsPersistenceManager::ReadPer"...
0x140052ba6  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140052bab  mov     rdx, rsi; int
0x140052bae  mov     ecx, edi; this
0x140052bb0  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140052bb5  call    _lambda_fd806375622af003ca3a1e8511b068d0___operator__
0x140052bba  mov     rcx, [r14+70h]
0x140052bbe  test    rcx, rcx
0x140052bc1  jz      short loc_140052BCF
0x140052bc3  mov     rax, [rcx]
0x140052bc6  mov     rax, [rax+18h]
0x140052bca  call    _guard_dispatch_icall
0x140052bcf  mov     eax, edi
0x140052bd1  jmp     loc_14005312C
0x140052bd6  cmp     qword ptr [rbp+4Fh+FileInformation+8], 0
0x140052bdb  jz      loc_140052F18
0x140052be1  mov     r15d, [r13+12Ch]
0x140052be8  lea     rdx, [r13+48h]
0x140052bec  lea     rcx, [rsp+130h+Buffer]
0x140052bf1  mov     [rsp+130h+Length], r15d
0x140052bf6  mov     qword ptr [rbp+4Fh+ByteOffset], 0
0x140052bfe  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140052c03  mov     rax, [r13+30h]
0x140052c07  mov     rbx, [rax+8]
0x140052c0b  mov     rdi, [rax]
0x140052c0e  test    rbx, rbx
0x140052c11  jz      short loc_140052C17
0x140052c13  lock inc dword ptr [rbx+8]
0x140052c17  mov     rcx, [rsp+130h+Buffer]; this
0x140052c1c  test    rcx, rcx
0x140052c1f  jz      short loc_140052C26
0x140052c21  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140052c26  mov     rdx, [rdi+8]
0x140052c2a  lea     rcx, [rsp+130h+Buffer]
0x140052c2f  mov     r8, r15
0x140052c32  mov     [rbp+4Fh+var_90], r15
0x140052c36  mov     rdx, [rdx]
0x140052c39  call    ??$make_unique_aligned_pool@$$BY0A@W4byte@gsl@@$00$0GNHAEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@PEAU_FLT_INSTANCE@@_K@Z; utl::make_unique_aligned_pool<gsl::byte [0],1,1836074581,0>(_FLT_INSTANCE *,unsigned __int64)
0x140052c3e  test    rbx, rbx
0x140052c41  jz      short loc_140052C4B
0x140052c43  mov     rcx, rbx; this
0x140052c46  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140052c4b  mov     rdi, [rsp+130h+Buffer]
0x140052c50  test    rdi, rdi
0x140052c53  jz      loc_1400530E4
0x140052c59  mov     eax, [rsp+130h+Length]
0x140052c5d  mov     cl, 1
0x140052c5f  xor     r15d, r15d
0x140052c62  mov     [rsp+130h+var_E0], cl
0x140052c66  mov     [rbp+4Fh+var_A0], r15
0x140052c6a  test    cl, cl
0x140052c6c  jnz     short loc_140052C7F
0x140052c6e  cmp     r15d, eax
0x140052c71  jnz     loc_140052E05
0x140052c77  mov     rax, [rbp+4Fh+var_90]
0x140052c7b  add     qword ptr [rbp+4Fh+ByteOffset], rax
0x140052c7f  lea     rdx, [r13+48h]
0x140052c83  mov     [rsp+130h+var_D0], 0
0x140052c8b  lea     rcx, [rsp+130h+Buffer]
0x140052c90  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140052c95  mov     rax, [r13+30h]
0x140052c99  mov     r15, [rax+8]
0x140052c9d  mov     rbx, [rax]
0x140052ca0  test    r15, r15
0x140052ca3  jz      short loc_140052CAA
0x140052ca5  lock inc dword ptr [r15+8]
0x140052caa  mov     rcx, [rsp+130h+Buffer]; this
0x140052caf  mov     [rsp+130h+Buffer], 0
0x140052cb8  test    rcx, rcx
0x140052cbb  jz      short loc_140052CC2
0x140052cbd  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140052cc2  mov     rcx, [rbx+8]
0x140052cc6  lea     rax, [rsp+130h+var_D0]
0x140052ccb  mov     r9d, [rsp+130h+Length]; Length
0x140052cd0  lea     r8, [rbp+4Fh+ByteOffset]; ByteOffset
0x140052cd4  mov     rdx, [rbp+4Fh+FileObject]; FileObject
0x140052cd8  mov     [rsp+130h+CallbackContext], 0; CallbackContext
0x140052ce1  mov     rcx, [rcx]; InitiatingInstance
0x140052ce4  mov     [rsp+130h+CallbackRoutine], 0; CallbackRoutine
0x140052ced  mov     [rsp+130h+BytesRead], rax; BytesRead
0x140052cf2  mov     dword ptr [rsp+130h+LengthReturned], 0; char *
0x140052cfa  mov     qword ptr [rsp+130h+FileInformationClass], rdi; Buffer
0x140052cff  call    cs:__imp_FltReadFile
0x140052d06  nop     dword ptr [rax+rax+00h]
0x140052d0b  mov     ebx, eax
0x140052d0d  test    r15, r15
0x140052d10  jz      short loc_140052D1A
0x140052d12  mov     rcx, r15; this
0x140052d15  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140052d1a  test    ebx, ebx
0x140052d1c  js      loc_1400530B8
0x140052d22  mov     r15d, [rsp+130h+Length]
0x140052d27  cmp     [rsp+130h+var_D0], r15d
0x140052d2c  jz      loc_140052DB8
0x140052d32  mov     eax, cs:dword_14009E178
0x140052d38  cmp     eax, 3
0x140052d3b  jbe     short loc_140052DB8
0x140052d3d  mov     rcx, cs:qword_14009E190
0x140052d44  mov     edx, 8000h
0x140052d49  mov     rax, cs:qword_14009E188
0x140052d50  test    rdx, rax
0x140052d53  jz      short loc_140052DB8
0x140052d55  mov     rax, rcx
0x140052d58  and     rax, rdx
0x140052d5b  cmp     rax, rcx
0x140052d5e  jnz     short loc_140052DB8
0x140052d60  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x140052d67  mov     dword ptr [rbp+4Fh+var_B0], 10Ah
0x140052d6e  mov     [rbp+4Fh+var_88], rax
0x140052d72  lea     rdx, byte_140098175
0x140052d79  lea     rax, aUnionfsUfspers_5; "UnionFs::UfsPersistenceManager::ReadPer"...
0x140052d80  mov     qword ptr [rbp+4Fh+var_80], rax
0x140052d84  lea     rax, aCouldNotReadEn; "Could not read entire payload chunk, ma"...
0x140052d8b  mov     [rbp+4Fh+var_78], rax
0x140052d8f  lea     rax, [rbp+4Fh+var_B0]
0x140052d93  mov     [rsp+130h+CallbackRoutine], rax
0x140052d98  lea     rax, [rbp+4Fh+var_88]
0x140052d9c  mov     [rsp+130h+BytesRead], rax
0x140052da1  lea     rax, [rbp+4Fh+var_80]
0x140052da5  mov     [rsp+130h+LengthReturned], rax; char *
0x140052daa  lea     rax, [rbp+4Fh+var_78]
0x140052dae  mov     qword ptr [rsp+130h+FileInformationClass], rax
0x140052db3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140052db8  xor     r15d, r15d
0x140052dbb  cmp     [rsp+130h+var_E0], r15b
0x140052dc0  jz      short loc_140052E05
0x140052dc2  mov     rax, [rdi]
0x140052dc5  lea     rdx, [rbp+4Fh+var_A0]
0x140052dc9  mov     [rbp+4Fh+var_A0], rax
0x140052dcd  mov     rcx, r12
0x140052dd0  mov     rax, [r12]
0x140052dd4  mov     rax, [rax+98h]
0x140052ddb  call    _guard_dispatch_icall
0x140052de0  test    al, al
0x140052de2  jnz     short loc_140052DF9
0x140052de4  mov     rax, [r12]
0x140052de8  mov     rdx, r13
0x140052deb  mov     rcx, r12
0x140052dee  mov     rax, [rax+18h]
0x140052df2  call    _guard_dispatch_icall
0x140052df7  jmp     short loc_140052DFF
0x140052df9  mov     r15d, 8
  ... truncated ...
```
