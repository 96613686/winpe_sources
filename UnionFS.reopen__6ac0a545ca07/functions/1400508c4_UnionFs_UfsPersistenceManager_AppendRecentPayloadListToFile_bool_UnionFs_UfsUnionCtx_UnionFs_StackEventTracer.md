# UnionFs::UfsPersistenceManager::AppendRecentPayloadListToFile(bool *,UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &)

- ea: `0x1400508c4`
- end: `0x140050ef0`
- name: `?AppendRecentPayloadListToFile@UfsPersistenceManager@UnionFs@@IEBAJPEA_NAEAVUfsUnionCtx@2@AEAVStackEventTracer@2@@Z`
- size: `1580`
- prototype: `int(UnionFs::UfsPersistenceManager *__hidden this, bool *, struct UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140052188`
- `0x140052508`

## callees

- `0x140001008`
- `0x14000f81c`
- `0x14001f4c8`
- `0x14004fee4`
- `0x1400506cc`
- `0x1400508c4`
- `0x140054048`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140079d44`
- `0x14007a0c0`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140050bdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050c40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050e43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050e63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050bdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050c40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050e43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050e63`
- `FLTMGR!FltReadFile` at `0x140050b89`
- `FLTMGR!FltReadFile` at `0x140050b89`
- `FLTMGR!FltQueryInformationFile` at `0x140050a2f`
- `FLTMGR!FltQueryInformationFile` at `0x140050a2f`

## string_xrefs

- `0x140050baa`: `API: Reading payload records`
- `0x140050c08`: `ORIGIN: Couldn't read full chunk`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPersistenceManager::AppendRecentPayloadListToFile(
        UnionFs::UfsPersistenceManager *this,
        bool *a2,
        struct UnionFs::UfsUnionCtx *a3,
        struct UnionFs::StackEventTracer *a4)
{
  __m128i si128; // xmm0
  __int64 v9; // rax
  struct _FILE_OBJECT *v10; // r12
  unsigned __int64 *v11; // rdx
  __int64 *v12; // rcx
  volatile signed __int32 *v13; // r14
  __int64 v14; // rdi
  int v15; // edi
  __int64 v16; // r13
  bool v17; // r12
  unsigned __int64 *v18; // rdx
  __int64 *v19; // rax
  volatile signed __int32 *v20; // rdi
  __int64 v21; // r14
  _QWORD *v22; // rdi
  unsigned __int64 *v23; // rdx
  __int64 *v24; // rax
  volatile signed __int32 *v25; // r14
  __int64 v26; // r12
  NTSTATUS v27; // r12d
  const char *v28; // rax
  __int64 v29; // r8
  unsigned int v30; // r14d
  _DWORD *v31; // r12
  __int64 v32; // rax
  unsigned int v33; // ecx
  unsigned __int64 *v34; // rdx
  __int64 *v35; // rax
  volatile signed __int32 *v36; // rdi
  __int64 v37; // r14
  struct _FLT_INSTANCE *v38; // r14
  const char *LengthReturned; // [rsp+28h] [rbp-B1h]
  const char *LengthReturneda; // [rsp+28h] [rbp-B1h]
  char *LengthReturnedb; // [rsp+28h] [rbp-B1h]
  bool v43; // [rsp+50h] [rbp-89h]
  PVOID Buffer; // [rsp+58h] [rbp-81h] BYREF
  FsFltWil::Details *v45; // [rsp+60h] [rbp-79h] BYREF
  ULONG BytesRead[2]; // [rsp+68h] [rbp-71h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp-69h] BYREF
  PFILE_OBJECT FileObject; // [rsp+78h] [rbp-61h] BYREF
  FsFltWil::Details *v49; // [rsp+80h] [rbp-59h] BYREF
  int v50; // [rsp+88h] [rbp-51h]
  unsigned int v51; // [rsp+8Ch] [rbp-4Dh]
  union _LARGE_INTEGER v52; // [rsp+90h] [rbp-49h]
  int v53; // [rsp+98h] [rbp-41h]
  unsigned int v54; // [rsp+9Ch] [rbp-3Dh]
  PVOID P; // [rsp+A0h] [rbp-39h]
  int v56; // [rsp+A8h] [rbp-31h]
  __m128i v57; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v58; // [rsp+C0h] [rbp-19h]
  char *v59; // [rsp+C8h] [rbp-11h]
  __int128 FileInformation; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v61; // [rsp+E0h] [rbp+7h]

  v59 = (char *)a2;
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x8000) != 0
    && (qword_14009E190 & 0x8000) == qword_14009E190 )
  {
    v45 = (FsFltWil::Details *)"UnionFs::UfsPersistenceManager::AppendRecentPayloadListToFile";
    FileObject = (PFILE_OBJECT)"onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
    LODWORD(Buffer) = 869;
    *(_QWORD *)BytesRead = "ENTER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)qword_140098030,
      0x8000,
      (_DWORD)a4,
      (__int64)BytesRead,
      (__int64)&v45,
      (__int64)&FileObject,
      (__int64)&Buffer);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v58 = -1;
  *a2 = 0;
  v9 = *(_QWORD *)this;
  v57 = si128;
  (*(void (__fastcall **)(UnionFs::UfsPersistenceManager *, struct UnionFs::UfsUnionCtx *, __m128i *, struct UnionFs::StackEventTracer *))(v9 + 48))(
    this,
    a3,
    &v57,
    a4);
  v10 = (struct _FILE_OBJECT *)(*(__int64 (__fastcall **)(UnionFs::UfsPersistenceManager *, struct UnionFs::UfsUnionCtx *))(*(_QWORD *)this + 96LL))(
                                 this,
                                 a3);
  FileObject = v10;
  v61 = 0;
  FileInformation = 0;
  FsFltWil::AcquirePushLockShared(&v45, (char *)a3 + 72);
  v12 = (__int64 *)*((_QWORD *)a3 + 6);
  v13 = (volatile signed __int32 *)v12[1];
  v14 = *v12;
  if ( v13 )
    _InterlockedIncrement(v13 + 2);
  if ( v45 )
    FsFltWil::Details::ReleasePushLockShared(v45, v11);
  v15 = FltQueryInformationFile(**(PFLT_INSTANCE **)(v14 + 8), v10, &FileInformation, 0x18u, FileStandardInformation, 0);
  if ( v13 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v13);
  if ( v15 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v15,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x2DF0017038FLL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::AppendRecentPayloadListToFile",
      "API: Querying standard info",
      LengthReturned);
LABEL_61:
    (*(void (__fastcall **)(UnionFs::UfsPersistenceManager *, struct UnionFs::UfsUnionCtx *))(*(_QWORD *)this + 24LL))(
      this,
      a3);
LABEL_66:
    utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(&v57);
    lambda_d9ee0d6754c3d0cf88198ab4242f9167_::operator()();
    return (unsigned int)v15;
  }
  ByteOffset.QuadPart = 0;
  v16 = *((unsigned int *)a3 + 75);
  v17 = *((_QWORD *)&FileInformation + 1) > 0LL;
  v43 = *((_QWORD *)&FileInformation + 1) > 0LL;
  LODWORD(v45) = 2 * v16;
  FsFltWil::AcquirePushLockShared(&Buffer, (char *)a3 + 72);
  v19 = (__int64 *)*((_QWORD *)a3 + 6);
  v20 = (volatile signed __int32 *)v19[1];
  v21 = *v19;
  if ( v20 )
    _InterlockedIncrement(v20 + 2);
  if ( Buffer )
    FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Buffer, v18);
  utl::make_unique_aligned_pool<enum gsl::byte [0],1,1836074581,0>(
    &Buffer,
    **(_QWORD **)(v21 + 8),
    (unsigned int)(2 * v16));
  if ( v20 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
  v22 = Buffer;
  if ( !Buffer )
  {
    v15 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x2D0001703AALL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::AppendRecentPayloadListToFile",
      "ORIGIN: Allocating payload info buffer",
      LengthReturned);
    (*(void (__fastcall **)(UnionFs::UfsPersistenceManager *, struct UnionFs::UfsUnionCtx *))(*(_QWORD *)this + 24LL))(
      this,
      a3);
    goto LABEL_66;
  }
  if ( v17 )
  {
    BytesRead[0] = 0;
    ByteOffset.QuadPart = *((_QWORD *)&FileInformation + 1) - v16;
    FsFltWil::AcquirePushLockShared(&v49, (char *)a3 + 72);
    v24 = (__int64 *)*((_QWORD *)a3 + 6);
    v25 = (volatile signed __int32 *)v24[1];
    v26 = *v24;
    if ( v25 )
      _InterlockedIncrement(v25 + 2);
    if ( v49 )
      FsFltWil::Details::ReleasePushLockShared(v49, v23);
    v27 = FltReadFile(**(PFLT_INSTANCE **)(v26 + 8), FileObject, &ByteOffset, v16, v22, 0, BytesRead, 0, 0);
    if ( v25 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v25);
    if ( v27 < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v27,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x2D6001703C0LL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::AppendRecentPayloadListToFile",
        "API: Reading payload records",
        LengthReturneda);
LABEL_29:
      if ( v22 )
        ExFreePoolWithTag(v22, 0);
      (*(void (__fastcall **)(UnionFs::UfsPersistenceManager *, struct UnionFs::UfsUnionCtx *))(*(_QWORD *)this + 24LL))(
        this,
        a3);
      v15 = v27;
      goto LABEL_66;
    }
    if ( BytesRead[0] != (_DWORD)v16 )
    {
      v28 = "ORIGIN: Couldn't read full chunk";
      v29 = 0x2D7001703C7LL;
LABEL_34:
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000102LL,
        (int)a4,
        (struct UnionFs::StackEventTracer *)v29,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::AppendRecentPayloadListToFile",
        v28,
        LengthReturneda);
      if ( v22 )
        ExFreePoolWithTag(v22, 0);
      (*(void (__fastcall **)(UnionFs::UfsPersistenceManager *, struct UnionFs::UfsUnionCtx *))(*(_QWORD *)this + 24LL))(
        this,
        a3);
      v15 = -1073741566;
      goto LABEL_66;
    }
    v30 = 0;
    if ( ByteOffset.QuadPart )
      goto LABEL_41;
    v49 = (FsFltWil::Details *)*v22;
    if ( !(*(unsigned __int8 (__fastcall **)(UnionFs::UfsPersistenceManager *, FsFltWil::Details **))(*(_QWORD *)this + 152LL))(
            this,
            &v49) )
    {
      v28 = "ORIGIN: Version header mismatch";
      v29 = 0x4B2001703D6LL;
      goto LABEL_34;
    }
    v30 = 8;
    do
    {
LABEL_41:
      v31 = (_DWORD *)((char *)v22 + v30);
      v30 += *v31;
      if ( v30 > (unsigned int)v16 )
      {
        v28 = "ORIGIN: Payload record extends beyond buffer";
        v29 = 0x538001703EBLL;
        goto LABEL_34;
      }
    }
    while ( *v31 );
    if ( v30 > *((_QWORD *)&FileInformation + 1) - 20LL )
      MicrosoftTelemetryAssertTriggeredMsgKM(
        "lastRecordNEOFieldOffset <= gsl::narrow_cast<LONGLONG>(originalStandardInfo.EndOfFile.QuadPart - sizeof(UFS_PAYL"
        "OAD_INFORMATION))");
    v32 = *(_QWORD *)this;
    LODWORD(Buffer) = 0;
    v27 = (*(__int64 (__fastcall **)(UnionFs::UfsPersistenceManager *, _DWORD *, PVOID *, struct UnionFs::StackEventTracer *))(v32 + 128))(
            this,
            v31,
            &Buffer,
            a4);
    if ( v27 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v27,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x664001703FBLL,
        (unsigned __int64)"UnionFs::UfsPersistenceManager::AppendRecentPayloadListToFile",
        "PUSH: Getting payload size",
        LengthReturneda);
      goto LABEL_29;
    }
    v17 = v43;
    v33 = v30 + (_DWORD)Buffer;
  }
  else
  {
    v30 = 0;
    v33 = 0;
  }
  v50 = 0;
  v52.QuadPart = 0;
  v56 = 0;
  if ( !v17 )
    v50 = 3;
  v52 = ByteOffset;
  v54 = v33;
  v53 = (int)v45;
  v51 = v30;
  P = v22;
  FsFltWil::AcquirePushLockShared(&v45, (char *)a3 + 72);
  v35 = (__int64 *)*((_QWORD *)a3 + 6);
  v36 = (volatile signed __int32 *)v35[1];
  v37 = *v35;
  if ( v36 )
    _InterlockedIncrement(v36 + 2);
  if ( v45 )
    FsFltWil::Details::ReleasePushLockShared(v45, v34);
  v38 = **(struct _FLT_INSTANCE ***)(v37 + 8);
  if ( v36 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v36);
  LengthReturnedb = v59;
  v15 = UnionFs::UfsPersistenceManager::WritePayloadsToFile(
          this,
          v38,
          FileObject,
          (ULONG *)a3,
          (struct UnionFs::UfsTablePayload ***)&v57);
  if ( v15 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v15,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x4B30017041FLL,
      (unsigned __int64)"UnionFs::UfsPersistenceManager::AppendRecentPayloadListToFile",
      "PUSH: Writing payload records",
      LengthReturnedb);
    if ( P )
      ExFreePoolWithTag(P, 0);
    goto LABEL_61;
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(&v57);
  lambda_d9ee0d6754c3d0cf88198ab4242f9167_::operator()();
  return 0;
}

```

## disassembly

```asm
0x1400508c4  push    rbp
0x1400508c6  push    rbx
0x1400508c7  push    rsi
0x1400508c8  push    rdi
0x1400508c9  push    r12
0x1400508cb  push    r13
0x1400508cd  push    r14
0x1400508cf  push    r15
0x1400508d1  lea     rbp, [rsp-1Fh]
0x1400508d6  sub     rsp, 0F8h
0x1400508dd  mov     rax, cs:__security_cookie
0x1400508e4  xor     rax, rsp
0x1400508e7  mov     [rbp+57h+var_48], rax
0x1400508eb  mov     eax, cs:dword_14009E178
0x1400508f1  mov     rdi, rdx
0x1400508f4  mov     [rbp+57h+var_68], rdx
0x1400508f8  mov     r15, r9
0x1400508fb  lea     rdx, aUnionfsUfspers_22; "UnionFs::UfsPersistenceManager::AppendR"...
0x140050902  mov     rsi, r8
0x140050905  mov     rbx, rcx
0x140050908  cmp     eax, 5
0x14005090b  jbe     short loc_140050984
0x14005090d  mov     rcx, cs:qword_14009E190
0x140050914  mov     r8d, 8000h
0x14005091a  mov     rax, cs:qword_14009E188
0x140050921  test    r8, rax
0x140050924  jz      short loc_140050984
0x140050926  mov     rax, rcx
0x140050929  and     rax, r8
0x14005092c  cmp     rax, rcx
0x14005092f  jnz     short loc_140050984
0x140050931  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x140050938  mov     [rbp+57h+var_D0], rdx
0x14005093c  mov     [rbp+57h+FileObject], rax
0x140050940  lea     rdx, qword_140098030
0x140050947  lea     rax, aEnter; "ENTER"
0x14005094e  mov     dword ptr [rsp+130h+Buffer], 365h
0x140050956  mov     qword ptr [rbp+57h+var_C8], rax
0x14005095a  lea     rax, [rsp+130h+Buffer]
0x14005095f  mov     [rsp+130h+CallbackRoutine], rax
0x140050964  lea     rax, [rbp+57h+FileObject]
0x140050968  mov     [rsp+130h+BytesRead], rax
0x14005096d  lea     rax, [rbp+57h+var_D0]
0x140050971  mov     [rsp+130h+LengthReturned], rax
0x140050976  lea     rax, [rbp+57h+var_C8]
0x14005097a  mov     qword ptr [rsp+130h+FileInformationClass], rax
0x14005097f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140050984  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14005098c  lea     r8, [rbp+57h+var_80]
0x140050990  xor     r13d, r13d
0x140050993  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x14005099b  mov     [rdi], r13b
0x14005099e  mov     r9, r15
0x1400509a1  mov     rax, [rbx]
0x1400509a4  mov     rdx, rsi
0x1400509a7  mov     rcx, rbx
0x1400509aa  movdqu  [rbp+57h+var_80], xmm0
0x1400509af  mov     rax, [rax+30h]
0x1400509b3  call    _guard_dispatch_icall
0x1400509b8  mov     rax, [rbx]
0x1400509bb  mov     rdx, rsi
0x1400509be  mov     rcx, rbx
0x1400509c1  mov     rax, [rax+60h]
0x1400509c5  call    _guard_dispatch_icall
0x1400509ca  mov     r12, rax
0x1400509cd  mov     [rbp+57h+FileObject], rax
0x1400509d1  xor     eax, eax
0x1400509d3  lea     rdx, [rsi+48h]
0x1400509d7  xorps   xmm0, xmm0
0x1400509da  mov     [rbp+57h+var_50], rax
0x1400509de  lea     rcx, [rbp+57h+var_D0]
0x1400509e2  movups  [rbp+57h+FileInformation], xmm0
0x1400509e6  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400509eb  mov     rcx, [rsi+30h]
0x1400509ef  mov     r14, [rcx+8]
0x1400509f3  mov     rdi, [rcx]
0x1400509f6  test    r14, r14
0x1400509f9  jz      short loc_140050A00
0x1400509fb  lock inc dword ptr [r14+8]
0x140050a00  mov     rcx, [rbp+57h+var_D0]; this
0x140050a04  test    rcx, rcx
0x140050a07  jz      short loc_140050A0E
0x140050a09  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140050a0e  mov     rcx, [rdi+8]
0x140050a12  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140050a16  mov     [rsp+130h+LengthReturned], r13; char *
0x140050a1b  mov     r9d, 18h; Length
0x140050a21  mov     rdx, r12; FileObject
0x140050a24  mov     [rsp+130h+FileInformationClass], 5; FileInformationClass
0x140050a2c  mov     rcx, [rcx]; Instance
0x140050a2f  call    cs:__imp_FltQueryInformationFile
0x140050a36  nop     dword ptr [rax+rax+00h]
0x140050a3b  mov     edi, eax
0x140050a3d  test    r14, r14
0x140050a40  jz      short loc_140050A4A
0x140050a42  mov     rcx, r14; this
0x140050a45  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140050a4a  test    edi, edi
0x140050a4c  jns     short loc_140050A7A
0x140050a4e  lea     rax, aApiQueryingSta; "API: Querying standard info"
0x140050a55  mov     r8, 2DF0017038Fh; struct UnionFs::StackEventTracer *
0x140050a5f  lea     r9, aUnionfsUfspers_22; "UnionFs::UfsPersistenceManager::AppendR"...
0x140050a66  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140050a6b  mov     rdx, r15; int
0x140050a6e  mov     ecx, edi; this
0x140050a70  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140050a75  jmp     loc_140050E4F
0x140050a7a  cmp     qword ptr [rbp+57h+FileInformation+8], 0
0x140050a7f  lea     rdx, [rsi+48h]
0x140050a83  mov     qword ptr [rbp+57h+ByteOffset], r13
0x140050a87  lea     rcx, [rsp+130h+Buffer]
0x140050a8c  mov     r13d, [rsi+12Ch]
0x140050a93  setnle  r12b
0x140050a97  mov     [rsp+130h+var_E0], r12b
0x140050a9c  lea     eax, ds:0[r13*2]
0x140050aa4  mov     dword ptr [rbp+57h+var_D0], eax
0x140050aa7  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140050aac  mov     rax, [rsi+30h]
0x140050ab0  mov     rdi, [rax+8]
0x140050ab4  mov     r14, [rax]
0x140050ab7  test    rdi, rdi
0x140050aba  jz      short loc_140050AC0
0x140050abc  lock inc dword ptr [rdi+8]
0x140050ac0  mov     rcx, [rsp+130h+Buffer]; this
0x140050ac5  test    rcx, rcx
0x140050ac8  jz      short loc_140050ACF
0x140050aca  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140050acf  mov     rdx, [r14+8]
0x140050ad3  lea     r8d, ds:0[r13*2]
0x140050adb  lea     rcx, [rsp+130h+Buffer]
0x140050ae0  mov     rdx, [rdx]
0x140050ae3  call    ??$make_unique_aligned_pool@$$BY0A@W4byte@gsl@@$00$0GNHAEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@PEAU_FLT_INSTANCE@@_K@Z; utl::make_unique_aligned_pool<gsl::byte [0],1,1836074581,0>(_FLT_INSTANCE *,unsigned __int64)
0x140050ae8  test    rdi, rdi
0x140050aeb  jz      short loc_140050AF5
0x140050aed  mov     rcx, rdi; this
0x140050af0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140050af5  mov     rdi, [rsp+130h+Buffer]
0x140050afa  test    rdi, rdi
0x140050afd  jz      loc_140050E81
0x140050b03  test    r12b, r12b
0x140050b06  jz      loc_140050D5F
0x140050b0c  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x140050b10  lea     rdx, [rsi+48h]
0x140050b14  sub     rcx, r13
0x140050b17  mov     [rbp+57h+var_C8], 0
0x140050b1e  mov     qword ptr [rbp+57h+ByteOffset], rcx
0x140050b22  lea     rcx, [rbp+57h+var_B0]
0x140050b26  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140050b2b  mov     rax, [rsi+30h]
0x140050b2f  mov     r14, [rax+8]
0x140050b33  mov     r12, [rax]
0x140050b36  test    r14, r14
0x140050b39  jz      short loc_140050B40
0x140050b3b  lock inc dword ptr [r14+8]
0x140050b40  mov     rcx, [rbp+57h+var_B0]; this
0x140050b44  test    rcx, rcx
0x140050b47  jz      short loc_140050B4E
0x140050b49  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140050b4e  mov     rcx, [r12+8]
0x140050b53  lea     rax, [rbp+57h+var_C8]
0x140050b57  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140050b5b  lea     r8, [rbp+57h+ByteOffset]; ByteOffset
0x140050b5f  mov     [rsp+130h+CallbackContext], 0; CallbackContext
0x140050b68  mov     r9d, r13d; Length
0x140050b6b  mov     [rsp+130h+CallbackRoutine], 0; CallbackRoutine
0x140050b74  mov     rcx, [rcx]; InitiatingInstance
0x140050b77  mov     [rsp+130h+BytesRead], rax; BytesRead
0x140050b7c  mov     dword ptr [rsp+130h+LengthReturned], 0; char *
0x140050b84  mov     qword ptr [rsp+130h+FileInformationClass], rdi; Buffer
0x140050b89  call    cs:__imp_FltReadFile
0x140050b90  nop     dword ptr [rax+rax+00h]
0x140050b95  mov     r12d, eax
0x140050b98  test    r14, r14
0x140050b9b  jz      short loc_140050BA5
0x140050b9d  mov     rcx, r14; this
0x140050ba0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140050ba5  test    r12d, r12d
0x140050ba8  jns     short loc_140050C02
0x140050baa  lea     rax, aApiReadingPayl; "API: Reading payload records"
0x140050bb1  mov     r8, 2D6001703C0h; struct UnionFs::StackEventTracer *
0x140050bbb  lea     r9, aUnionfsUfspers_22; "UnionFs::UfsPersistenceManager::AppendR"...
0x140050bc2  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140050bc7  mov     rdx, r15; int
0x140050bca  mov     ecx, r12d; this
0x140050bcd  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140050bd2  test    rdi, rdi
0x140050bd5  jz      short loc_140050BE8
0x140050bd7  xor     edx, edx; Tag
0x140050bd9  mov     rcx, rdi; P
0x140050bdc  call    cs:__imp_ExFreePoolWithTag
0x140050be3  nop     dword ptr [rax+rax+00h]
0x140050be8  mov     rax, [rbx]
0x140050beb  mov     rdx, rsi
0x140050bee  mov     rcx, rbx
0x140050bf1  mov     rax, [rax+18h]
0x140050bf5  call    _guard_dispatch_icall
0x140050bfa  mov     edi, r12d
0x140050bfd  jmp     loc_140050EBF
0x140050c02  cmp     [rbp+57h+var_C8], r13d
0x140050c06  jz      short loc_140050C66
0x140050c08  lea     rax, aOriginCouldnTR; "ORIGIN: Couldn't read full chunk"
0x140050c0f  mov     r8, 2D7001703C7h; struct UnionFs::StackEventTracer *
0x140050c19  mov     r14d, 0C0000102h
0x140050c1f  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140050c24  mov     ecx, r14d; this
0x140050c27  lea     r9, aUnionfsUfspers_22; "UnionFs::UfsPersistenceManager::AppendR"...
0x140050c2e  mov     rdx, r15; int
0x140050c31  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140050c36  test    rdi, rdi
0x140050c39  jz      short loc_140050C4C
0x140050c3b  xor     edx, edx; Tag
0x140050c3d  mov     rcx, rdi; P
0x140050c40  call    cs:__imp_ExFreePoolWithTag
0x140050c47  nop     dword ptr [rax+rax+00h]
0x140050c4c  mov     rax, [rbx]
0x140050c4f  mov     rdx, rsi
0x140050c52  mov     rcx, rbx
0x140050c55  mov     rax, [rax+18h]
0x140050c59  call    _guard_dispatch_icall
0x140050c5e  mov     edi, r14d
0x140050c61  jmp     loc_140050EBF
0x140050c66  xor     r14d, r14d
0x140050c69  cmp     qword ptr [rbp+57h+ByteOffset], r14
0x140050c6d  jnz     short loc_140050CAC
0x140050c6f  mov     rax, [rdi]
0x140050c72  lea     rdx, [rbp+57h+var_B0]
0x140050c76  mov     [rbp+57h+var_B0], rax
0x140050c7a  mov     rcx, rbx
0x140050c7d  mov     rax, [rbx]
0x140050c80  mov     rax, [rax+98h]
0x140050c87  call    _guard_dispatch_icall
0x140050c8c  test    al, al
0x140050c8e  jnz     short loc_140050CA6
0x140050c90  lea     rax, aOriginVersionH; "ORIGIN: Version header mismatch"
0x140050c97  mov     r8, 4B2001703D6h
0x140050ca1  jmp     loc_140050C19
0x140050ca6  mov     r14d, 8
0x140050cac  mov     r12d, r14d
0x140050caf  add     r12, rdi
0x140050cb2  mov     eax, [r12]
0x140050cb6  add     r14d, eax
0x140050cb9  cmp     r14d, r13d
0x140050cbc  ja      loc_140050D49
0x140050cc2  test    eax, eax
0x140050cc4  jnz     short loc_140050CAC
0x140050cc6  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x140050cca  add     rcx, 0FFFFFFFFFFFFFFECh
0x140050cce  mov     eax, r14d
0x140050cd1  cmp     rax, rcx
0x140050cd4  jle     short loc_140050CE2
0x140050cd6  lea     rcx, aLastrecordneof; "lastRecordNEOFieldOffset <= gsl::narrow"...
0x140050cdd  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140050ce2  mov     rax, [rbx]
0x140050ce5  lea     r8, [rsp+130h+Buffer]
0x140050cea  mov     r9, r15
0x140050ced  mov     dword ptr [rsp+130h+Buffer], 0
0x140050cf5  mov     rdx, r12
0x140050cf8  mov     rcx, rbx
0x140050cfb  mov     rax, [rax+80h]
0x140050d02  call    _guard_dispatch_icall
0x140050d07  mov     r12d, eax
0x140050d0a  test    eax, eax
0x140050d0c  jns     short loc_140050D3B
0x140050d0e  lea     rax, aPushGettingPay; "PUSH: Getting payload size"
0x140050d15  mov     r8, 664001703FBh; struct UnionFs::StackEventTracer *
0x140050d1f  lea     r9, aUnionfsUfspers_22; "UnionFs::UfsPersistenceManager::AppendR"...
0x140050d26  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140050d2b  mov     rdx, r15; int
0x140050d2e  mov     ecx, r12d; this
0x140050d31  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140050d36  jmp     loc_140050BD2
0x140050d3b  mov     ecx, dword ptr [rsp+130h+Buffer]
0x140050d3f  mov     r12b, [rsp+130h+var_E0]
0x140050d44  add     ecx, r14d
0x140050d47  jmp     short loc_140050D64
0x140050d49  lea     rax, aOriginPayloadR; "ORIGIN: Payload record extends beyond b"...
0x140050d50  mov     r8, 538001703EBh
0x140050d5a  jmp     loc_140050C19
0x140050d5f  xor     r14d, r14d
0x140050d62  xor     ecx, ecx
0x140050d64  xor     eax, eax
0x140050d66  xor     edx, edx
0x140050d68  mov     [rbp+57h+var_A8], eax
0x140050d6b  mov     [rbp+57h+var_A0], rdx
0x140050d6f  mov     [rbp+57h+var_88], eax
0x140050d72  test    r12b, r12b
0x140050d75  jnz     short loc_140050D7D
0x140050d77  or      eax, 3
0x140050d7a  mov     [rbp+57h+var_A8], eax
0x140050d7d  mov     rax, qword ptr [rbp+57h+ByteOffset]
0x140050d81  lea     rdx, [rsi+48h]
0x140050d85  mov     [rbp+57h+var_A0], rax
0x140050d89  mov     eax, dword ptr [rbp+57h+var_D0]
0x140050d8c  mov     [rbp+57h+var_94], ecx
0x140050d8f  lea     rcx, [rbp+57h+var_D0]
0x140050d93  mov     [rbp+57h+var_98], eax
0x140050d96  mov     [rbp+57h+var_A4], r14d
0x140050d9a  mov     [rbp+57h+P], rdi
0x140050d9e  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140050da3  mov     rax, [rsi+30h]
  ... truncated ...
```
