# UnionFs::UfsPersistenceManager::AppendRecentPayloadListToFile(bool *,UnionFs::UfsUnionCtx &,UnionFs::StackEventTracer &)

- ea: `0x140050744`
- end: `0x140050d70`
- name: `?AppendRecentPayloadListToFile@UfsPersistenceManager@UnionFs@@IEBAJPEA_NAEAVUfsUnionCtx@2@AEAVStackEventTracer@2@@Z`
- size: `1580`
- prototype: `int(UnionFs::UfsPersistenceManager *__hidden this, bool *, struct UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140052008`
- `0x140052388`

## callees

- `0x140001008`
- `0x14000f7fc`
- `0x14001f428`
- `0x14004fd64`
- `0x14005054c`
- `0x140050744`
- `0x140053ec8`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140079a24`
- `0x140079da0`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140050a5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050ac0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050cc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050ce3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050a5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050ac0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050cc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050ce3`
- `FLTMGR!FltReadFile` at `0x140050a09`
- `FLTMGR!FltReadFile` at `0x140050a09`
- `FLTMGR!FltQueryInformationFile` at `0x1400508af`
- `FLTMGR!FltQueryInformationFile` at `0x1400508af`

## string_xrefs

- `0x140050a2a`: `API: Reading payload records`
- `0x140050a88`: `ORIGIN: Couldn't read full chunk`

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
      (unsigned int)qword_140097FB0,
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
0x140050744  push    rbp
0x140050746  push    rbx
0x140050747  push    rsi
0x140050748  push    rdi
0x140050749  push    r12
0x14005074b  push    r13
0x14005074d  push    r14
0x14005074f  push    r15
0x140050751  lea     rbp, [rsp-1Fh]
0x140050756  sub     rsp, 0F8h
0x14005075d  mov     rax, cs:__security_cookie
0x140050764  xor     rax, rsp
0x140050767  mov     [rbp+57h+var_48], rax
0x14005076b  mov     eax, cs:dword_14009E178
0x140050771  mov     rdi, rdx
0x140050774  mov     [rbp+57h+var_68], rdx
0x140050778  mov     r15, r9
0x14005077b  lea     rdx, aUnionfsUfspers_22; "UnionFs::UfsPersistenceManager::AppendR"...
0x140050782  mov     rsi, r8
0x140050785  mov     rbx, rcx
0x140050788  cmp     eax, 5
0x14005078b  jbe     short loc_140050804
0x14005078d  mov     rcx, cs:qword_14009E190
0x140050794  mov     r8d, 8000h
0x14005079a  mov     rax, cs:qword_14009E188
0x1400507a1  test    r8, rax
0x1400507a4  jz      short loc_140050804
0x1400507a6  mov     rax, rcx
0x1400507a9  and     rax, r8
0x1400507ac  cmp     rax, rcx
0x1400507af  jnz     short loc_140050804
0x1400507b1  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x1400507b8  mov     [rbp+57h+var_D0], rdx
0x1400507bc  mov     [rbp+57h+FileObject], rax
0x1400507c0  lea     rdx, qword_140097FB0
0x1400507c7  lea     rax, aEnter; "ENTER"
0x1400507ce  mov     dword ptr [rsp+130h+Buffer], 365h
0x1400507d6  mov     qword ptr [rbp+57h+var_C8], rax
0x1400507da  lea     rax, [rsp+130h+Buffer]
0x1400507df  mov     [rsp+130h+CallbackRoutine], rax
0x1400507e4  lea     rax, [rbp+57h+FileObject]
0x1400507e8  mov     [rsp+130h+BytesRead], rax
0x1400507ed  lea     rax, [rbp+57h+var_D0]
0x1400507f1  mov     [rsp+130h+LengthReturned], rax
0x1400507f6  lea     rax, [rbp+57h+var_C8]
0x1400507fa  mov     qword ptr [rsp+130h+FileInformationClass], rax
0x1400507ff  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140050804  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14005080c  lea     r8, [rbp+57h+var_80]
0x140050810  xor     r13d, r13d
0x140050813  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x14005081b  mov     [rdi], r13b
0x14005081e  mov     r9, r15
0x140050821  mov     rax, [rbx]
0x140050824  mov     rdx, rsi
0x140050827  mov     rcx, rbx
0x14005082a  movdqu  [rbp+57h+var_80], xmm0
0x14005082f  mov     rax, [rax+30h]
0x140050833  call    _guard_dispatch_icall
0x140050838  mov     rax, [rbx]
0x14005083b  mov     rdx, rsi
0x14005083e  mov     rcx, rbx
0x140050841  mov     rax, [rax+60h]
0x140050845  call    _guard_dispatch_icall
0x14005084a  mov     r12, rax
0x14005084d  mov     [rbp+57h+FileObject], rax
0x140050851  xor     eax, eax
0x140050853  lea     rdx, [rsi+48h]
0x140050857  xorps   xmm0, xmm0
0x14005085a  mov     [rbp+57h+var_50], rax
0x14005085e  lea     rcx, [rbp+57h+var_D0]
0x140050862  movups  [rbp+57h+FileInformation], xmm0
0x140050866  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14005086b  mov     rcx, [rsi+30h]
0x14005086f  mov     r14, [rcx+8]
0x140050873  mov     rdi, [rcx]
0x140050876  test    r14, r14
0x140050879  jz      short loc_140050880
0x14005087b  lock inc dword ptr [r14+8]
0x140050880  mov     rcx, [rbp+57h+var_D0]; this
0x140050884  test    rcx, rcx
0x140050887  jz      short loc_14005088E
0x140050889  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14005088e  mov     rcx, [rdi+8]
0x140050892  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140050896  mov     [rsp+130h+LengthReturned], r13; char *
0x14005089b  mov     r9d, 18h; Length
0x1400508a1  mov     rdx, r12; FileObject
0x1400508a4  mov     [rsp+130h+FileInformationClass], 5; FileInformationClass
0x1400508ac  mov     rcx, [rcx]; Instance
0x1400508af  call    cs:__imp_FltQueryInformationFile
0x1400508b6  nop     dword ptr [rax+rax+00h]
0x1400508bb  mov     edi, eax
0x1400508bd  test    r14, r14
0x1400508c0  jz      short loc_1400508CA
0x1400508c2  mov     rcx, r14; this
0x1400508c5  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400508ca  test    edi, edi
0x1400508cc  jns     short loc_1400508FA
0x1400508ce  lea     rax, aApiQueryingSta; "API: Querying standard info"
0x1400508d5  mov     r8, 2DF0017038Fh; struct UnionFs::StackEventTracer *
0x1400508df  lea     r9, aUnionfsUfspers_22; "UnionFs::UfsPersistenceManager::AppendR"...
0x1400508e6  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x1400508eb  mov     rdx, r15; int
0x1400508ee  mov     ecx, edi; this
0x1400508f0  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400508f5  jmp     loc_140050CCF
0x1400508fa  cmp     qword ptr [rbp+57h+FileInformation+8], 0
0x1400508ff  lea     rdx, [rsi+48h]
0x140050903  mov     qword ptr [rbp+57h+ByteOffset], r13
0x140050907  lea     rcx, [rsp+130h+Buffer]
0x14005090c  mov     r13d, [rsi+12Ch]
0x140050913  setnle  r12b
0x140050917  mov     [rsp+130h+var_E0], r12b
0x14005091c  lea     eax, ds:0[r13*2]
0x140050924  mov     dword ptr [rbp+57h+var_D0], eax
0x140050927  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14005092c  mov     rax, [rsi+30h]
0x140050930  mov     rdi, [rax+8]
0x140050934  mov     r14, [rax]
0x140050937  test    rdi, rdi
0x14005093a  jz      short loc_140050940
0x14005093c  lock inc dword ptr [rdi+8]
0x140050940  mov     rcx, [rsp+130h+Buffer]; this
0x140050945  test    rcx, rcx
0x140050948  jz      short loc_14005094F
0x14005094a  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14005094f  mov     rdx, [r14+8]
0x140050953  lea     r8d, ds:0[r13*2]
0x14005095b  lea     rcx, [rsp+130h+Buffer]
0x140050960  mov     rdx, [rdx]
0x140050963  call    ??$make_unique_aligned_pool@$$BY0A@W4byte@gsl@@$00$0GNHAEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@PEAU_FLT_INSTANCE@@_K@Z; utl::make_unique_aligned_pool<gsl::byte [0],1,1836074581,0>(_FLT_INSTANCE *,unsigned __int64)
0x140050968  test    rdi, rdi
0x14005096b  jz      short loc_140050975
0x14005096d  mov     rcx, rdi; this
0x140050970  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140050975  mov     rdi, [rsp+130h+Buffer]
0x14005097a  test    rdi, rdi
0x14005097d  jz      loc_140050D01
0x140050983  test    r12b, r12b
0x140050986  jz      loc_140050BDF
0x14005098c  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x140050990  lea     rdx, [rsi+48h]
0x140050994  sub     rcx, r13
0x140050997  mov     [rbp+57h+var_C8], 0
0x14005099e  mov     qword ptr [rbp+57h+ByteOffset], rcx
0x1400509a2  lea     rcx, [rbp+57h+var_B0]
0x1400509a6  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400509ab  mov     rax, [rsi+30h]
0x1400509af  mov     r14, [rax+8]
0x1400509b3  mov     r12, [rax]
0x1400509b6  test    r14, r14
0x1400509b9  jz      short loc_1400509C0
0x1400509bb  lock inc dword ptr [r14+8]
0x1400509c0  mov     rcx, [rbp+57h+var_B0]; this
0x1400509c4  test    rcx, rcx
0x1400509c7  jz      short loc_1400509CE
0x1400509c9  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400509ce  mov     rcx, [r12+8]
0x1400509d3  lea     rax, [rbp+57h+var_C8]
0x1400509d7  mov     rdx, [rbp+57h+FileObject]; FileObject
0x1400509db  lea     r8, [rbp+57h+ByteOffset]; ByteOffset
0x1400509df  mov     [rsp+130h+CallbackContext], 0; CallbackContext
0x1400509e8  mov     r9d, r13d; Length
0x1400509eb  mov     [rsp+130h+CallbackRoutine], 0; CallbackRoutine
0x1400509f4  mov     rcx, [rcx]; InitiatingInstance
0x1400509f7  mov     [rsp+130h+BytesRead], rax; BytesRead
0x1400509fc  mov     dword ptr [rsp+130h+LengthReturned], 0; char *
0x140050a04  mov     qword ptr [rsp+130h+FileInformationClass], rdi; Buffer
0x140050a09  call    cs:__imp_FltReadFile
0x140050a10  nop     dword ptr [rax+rax+00h]
0x140050a15  mov     r12d, eax
0x140050a18  test    r14, r14
0x140050a1b  jz      short loc_140050A25
0x140050a1d  mov     rcx, r14; this
0x140050a20  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140050a25  test    r12d, r12d
0x140050a28  jns     short loc_140050A82
0x140050a2a  lea     rax, aApiReadingPayl; "API: Reading payload records"
0x140050a31  mov     r8, 2D6001703C0h; struct UnionFs::StackEventTracer *
0x140050a3b  lea     r9, aUnionfsUfspers_22; "UnionFs::UfsPersistenceManager::AppendR"...
0x140050a42  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140050a47  mov     rdx, r15; int
0x140050a4a  mov     ecx, r12d; this
0x140050a4d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140050a52  test    rdi, rdi
0x140050a55  jz      short loc_140050A68
0x140050a57  xor     edx, edx; Tag
0x140050a59  mov     rcx, rdi; P
0x140050a5c  call    cs:__imp_ExFreePoolWithTag
0x140050a63  nop     dword ptr [rax+rax+00h]
0x140050a68  mov     rax, [rbx]
0x140050a6b  mov     rdx, rsi
0x140050a6e  mov     rcx, rbx
0x140050a71  mov     rax, [rax+18h]
0x140050a75  call    _guard_dispatch_icall
0x140050a7a  mov     edi, r12d
0x140050a7d  jmp     loc_140050D3F
0x140050a82  cmp     [rbp+57h+var_C8], r13d
0x140050a86  jz      short loc_140050AE6
0x140050a88  lea     rax, aOriginCouldnTR; "ORIGIN: Couldn't read full chunk"
0x140050a8f  mov     r8, 2D7001703C7h; struct UnionFs::StackEventTracer *
0x140050a99  mov     r14d, 0C0000102h
0x140050a9f  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140050aa4  mov     ecx, r14d; this
0x140050aa7  lea     r9, aUnionfsUfspers_22; "UnionFs::UfsPersistenceManager::AppendR"...
0x140050aae  mov     rdx, r15; int
0x140050ab1  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140050ab6  test    rdi, rdi
0x140050ab9  jz      short loc_140050ACC
0x140050abb  xor     edx, edx; Tag
0x140050abd  mov     rcx, rdi; P
0x140050ac0  call    cs:__imp_ExFreePoolWithTag
0x140050ac7  nop     dword ptr [rax+rax+00h]
0x140050acc  mov     rax, [rbx]
0x140050acf  mov     rdx, rsi
0x140050ad2  mov     rcx, rbx
0x140050ad5  mov     rax, [rax+18h]
0x140050ad9  call    _guard_dispatch_icall
0x140050ade  mov     edi, r14d
0x140050ae1  jmp     loc_140050D3F
0x140050ae6  xor     r14d, r14d
0x140050ae9  cmp     qword ptr [rbp+57h+ByteOffset], r14
0x140050aed  jnz     short loc_140050B2C
0x140050aef  mov     rax, [rdi]
0x140050af2  lea     rdx, [rbp+57h+var_B0]
0x140050af6  mov     [rbp+57h+var_B0], rax
0x140050afa  mov     rcx, rbx
0x140050afd  mov     rax, [rbx]
0x140050b00  mov     rax, [rax+98h]
0x140050b07  call    _guard_dispatch_icall
0x140050b0c  test    al, al
0x140050b0e  jnz     short loc_140050B26
0x140050b10  lea     rax, aOriginVersionH; "ORIGIN: Version header mismatch"
0x140050b17  mov     r8, 4B2001703D6h
0x140050b21  jmp     loc_140050A99
0x140050b26  mov     r14d, 8
0x140050b2c  mov     r12d, r14d
0x140050b2f  add     r12, rdi
0x140050b32  mov     eax, [r12]
0x140050b36  add     r14d, eax
0x140050b39  cmp     r14d, r13d
0x140050b3c  ja      loc_140050BC9
0x140050b42  test    eax, eax
0x140050b44  jnz     short loc_140050B2C
0x140050b46  mov     rcx, qword ptr [rbp+57h+FileInformation+8]
0x140050b4a  add     rcx, 0FFFFFFFFFFFFFFECh
0x140050b4e  mov     eax, r14d
0x140050b51  cmp     rax, rcx
0x140050b54  jle     short loc_140050B62
0x140050b56  lea     rcx, aLastrecordneof; "lastRecordNEOFieldOffset <= gsl::narrow"...
0x140050b5d  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140050b62  mov     rax, [rbx]
0x140050b65  lea     r8, [rsp+130h+Buffer]
0x140050b6a  mov     r9, r15
0x140050b6d  mov     dword ptr [rsp+130h+Buffer], 0
0x140050b75  mov     rdx, r12
0x140050b78  mov     rcx, rbx
0x140050b7b  mov     rax, [rax+80h]
0x140050b82  call    _guard_dispatch_icall
0x140050b87  mov     r12d, eax
0x140050b8a  test    eax, eax
0x140050b8c  jns     short loc_140050BBB
0x140050b8e  lea     rax, aPushGettingPay; "PUSH: Getting payload size"
0x140050b95  mov     r8, 664001703FBh; struct UnionFs::StackEventTracer *
0x140050b9f  lea     r9, aUnionfsUfspers_22; "UnionFs::UfsPersistenceManager::AppendR"...
0x140050ba6  mov     qword ptr [rsp+130h+FileInformationClass], rax; char *
0x140050bab  mov     rdx, r15; int
0x140050bae  mov     ecx, r12d; this
0x140050bb1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140050bb6  jmp     loc_140050A52
0x140050bbb  mov     ecx, dword ptr [rsp+130h+Buffer]
0x140050bbf  mov     r12b, [rsp+130h+var_E0]
0x140050bc4  add     ecx, r14d
0x140050bc7  jmp     short loc_140050BE4
0x140050bc9  lea     rax, aOriginPayloadR; "ORIGIN: Payload record extends beyond b"...
0x140050bd0  mov     r8, 538001703EBh
0x140050bda  jmp     loc_140050A99
0x140050bdf  xor     r14d, r14d
0x140050be2  xor     ecx, ecx
0x140050be4  xor     eax, eax
0x140050be6  xor     edx, edx
0x140050be8  mov     [rbp+57h+var_A8], eax
0x140050beb  mov     [rbp+57h+var_A0], rdx
0x140050bef  mov     [rbp+57h+var_88], eax
0x140050bf2  test    r12b, r12b
0x140050bf5  jnz     short loc_140050BFD
0x140050bf7  or      eax, 3
0x140050bfa  mov     [rbp+57h+var_A8], eax
0x140050bfd  mov     rax, qword ptr [rbp+57h+ByteOffset]
0x140050c01  lea     rdx, [rsi+48h]
0x140050c05  mov     [rbp+57h+var_A0], rax
0x140050c09  mov     eax, dword ptr [rbp+57h+var_D0]
0x140050c0c  mov     [rbp+57h+var_94], ecx
0x140050c0f  lea     rcx, [rbp+57h+var_D0]
0x140050c13  mov     [rbp+57h+var_98], eax
0x140050c16  mov     [rbp+57h+var_A4], r14d
0x140050c1a  mov     [rbp+57h+P], rdi
0x140050c1e  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140050c23  mov     rax, [rsi+30h]
  ... truncated ...
```
