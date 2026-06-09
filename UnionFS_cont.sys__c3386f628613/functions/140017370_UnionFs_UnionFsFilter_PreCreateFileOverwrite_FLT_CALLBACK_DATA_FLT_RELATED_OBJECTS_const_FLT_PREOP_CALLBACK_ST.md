# UnionFs::UnionFsFilter::PreCreateFileOverwrite(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x140017370`
- end: `0x140018346`
- name: `?PreCreateFileOverwrite@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `4054`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x140011e00`

## callees

- `0x140002354`
- `0x14000efd0`
- `0x14000f7fc`
- `0x140010b88`
- `0x140010f54`
- `0x140011198`
- `0x1400114c4`
- `0x140017370`
- `0x14003cd88`
- `0x1400419a8`
- `0x1400438e4`
- `0x14004397c`
- `0x140043ef4`
- `0x140056ac4`
- `0x140056afc`
- `0x140060ed8`
- `0x1400610fc`
- `0x14006bca8`
- `0x1400702e4`
- `0x140077f94`
- `0x140078304`
- `0x140079a6c`
- `0x140079c48`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400178cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017949`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017a9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017b1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017bb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017bf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017c27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017d05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017d41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017d92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017dcf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017f50`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400182fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400178cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017949`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017a9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017b1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017bb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017bf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017c27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017d05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017d41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017d92`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017dcf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017f50`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400182fe`
- `ntoskrnl!PsGetHostSilo` at `0x140017574`
- `ntoskrnl!PsGetHostSilo` at `0x140017574`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017717`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017770`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400177b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400177f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001809d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017717`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017770`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400177b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400177f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001809d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017723`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001777c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400177c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400177fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400180a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017723`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001777c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400177c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400177fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400180a9`
- `FLTMGR!FltReferenceContext` at `0x140017636`
- `FLTMGR!FltReferenceContext` at `0x140017636`
- `FLTMGR!FltReleaseContext` at `0x14001773d`
- `FLTMGR!FltReleaseContext` at `0x140017796`
- `FLTMGR!FltReleaseContext` at `0x1400177d7`
- `FLTMGR!FltReleaseContext` at `0x14001773d`
- `FLTMGR!FltReleaseContext` at `0x140017796`
- `FLTMGR!FltReleaseContext` at `0x1400177d7`

## string_xrefs

- `0x140017452`: `PUSH: Cache lookup`
- `0x1400174fb`: `results.CacheEntry->GetOriginalScratchPath()`
- `0x140017901`: `PUSH: Allocating scratch path for layer lookup`
- `0x1400174a4`: `!FlagOn(Cbd.Iopb->Parameters.Create.Options, FILE_DIRECTORY_FILE)`
- `0x1400176e7`: `PUSH: Oplock and share access check`
- `0x14001753b`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x1400175fc`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x1400176f8`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x14001788c`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x140017a5e`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x140017ae4`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x140017b82`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x140017cd2`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x140017e5f`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x140017f05`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x14001801e`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x14001810e`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x1400181f6`: `UnionFs::UnionFsFilter::PreCreateFileOverwrite`
- `0x14001751c`: `Failing overwrite on exact match for renamed tombstone`
- `0x140017528`: `ORIGIN: Attempt to overwrite a directory by opening it as a non-directory`
- `0x140017f90`: `!layer && !fullPathInLayer`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCreateFileOverwrite(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        enum _FLT_PREOP_CALLBACK_STATUS *a4,
        struct UnionFs::CreateContext *a5,
        struct UnionFs::StackEventTracer *a6,
        const struct UnionFs::UfsSiloCtx *a7)
{
  int v8; // edi
  PFILE_OBJECT FileObject; // rax
  ULONG v11; // r9d
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // ebx
  const char *v16; // rax
  __int64 v17; // r8
  unsigned __int8 v18; // r14
  NTSTATUS v19; // r14d
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int *HostSilo; // r8
  utl::_RefCountBase *v23; // rax
  volatile signed __int32 *v24; // rdi
  __int64 v25; // rcx
  __int64 v26; // rdx
  utl::_RefCountBase *v27; // rbx
  struct UnionFs::UfsStreamHandleCtx *v28; // rbx
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  PACCESS_STATE AccessState; // rax
  __int64 v31; // rcx
  struct _ERESOURCE *v32; // rcx
  utl::_RefCountBase *v33; // rcx
  UnionFs::Rtl *v34; // rcx
  struct _UNICODE_STRING *v35; // rdx
  struct UnionFs::StackEventTracer *v36; // r9
  const char *v37; // rax
  __int64 v38; // r8
  struct _UNICODE_STRING *v39; // rdx
  struct _UNICODE_STRING *v40; // rbx
  bool v41; // zf
  PFLT_CONTEXT v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rbx
  utl::_RefCountBase *v45; // r10
  const struct UnionFs::UfsLayerCtx *v46; // r12
  volatile signed __int32 *v47; // rdi
  struct _UNICODE_STRING *v48; // rdx
  __int64 v49; // r8
  int v50; // r12d
  __int16 v51; // ax
  unsigned __int16 v52; // ax
  __int64 v53; // rcx
  NTSTATUS v54; // r14d
  struct _UNICODE_STRING *v55; // rdx
  struct _UNICODE_STRING *v56; // rbx
  unsigned __int16 *v57; // rbx
  struct _UNICODE_STRING *v58; // rdx
  struct _UNICODE_STRING *v59; // rbx
  __int64 v60; // rcx
  int v61; // eax
  utl::_RefCountBase *v62; // rcx
  utl::_RefCountBase *v63; // rcx
  struct _UNICODE_STRING *v64; // rbx
  int v65; // eax
  int v66; // r14d
  struct _UNICODE_STRING *v67; // rdx
  utl::_RefCountBase *v68; // rcx
  struct _UNICODE_STRING *v69; // rbx
  bool v70; // zf
  int v71; // eax
  _DWORD *v72; // rax
  utl::_RefCountBase *v73; // rcx
  utl::_RefCountBase *v74; // rcx
  int IsFileCowable; // eax
  bool v76; // al
  struct _UNICODE_STRING *v77; // rdx
  struct _UNICODE_STRING *v78; // rbx
  volatile signed __int32 *v79; // rbx
  __int64 v80; // r8
  volatile signed __int32 *v81; // rax
  utl::_RefCountBase *v82; // rax
  utl::_RefCountBase *v83; // rcx
  utl::_RefCountBase *v84; // rcx
  struct _ERESOURCE *v85; // rcx
  struct _FLT_RELATED_OBJECTS *v86; // rbx
  utl::_RefCountBase *v87; // rcx
  utl::_RefCountBase *v88; // rax
  utl::_RefCountBase *v89; // rcx
  struct _UNICODE_STRING *v90; // rdx
  struct _UNICODE_STRING *v91; // rdx
  _DWORD *v92; // rax
  struct _UNICODE_STRING *v93; // rbx
  struct UnionFs::UfsStreamHandleCtx *v95; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v96; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v97; // [rsp+28h] [rbp-D8h]
  char v98[8]; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v100[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v101; // [rsp+70h] [rbp-90h]
  char v102; // [rsp+74h] [rbp-8Ch]
  __int16 v103; // [rsp+75h] [rbp-8Bh]
  char v104; // [rsp+77h] [rbp-89h]
  PFLT_CONTEXT Context[2]; // [rsp+78h] [rbp-88h] BYREF
  PERESOURCE Resource[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v107; // [rsp+98h] [rbp-68h] BYREF
  char v108; // [rsp+A0h] [rbp-60h]
  __int128 v109; // [rsp+B0h] [rbp-50h] BYREF
  utl::_RefCountBase *v110[2]; // [rsp+C0h] [rbp-40h]
  PERESOURCE v111; // [rsp+D0h] [rbp-30h]
  __int64 v112; // [rsp+D8h] [rbp-28h]
  __int128 v113; // [rsp+E0h] [rbp-20h]
  struct UnionFs::UfsSiloCtx *v114; // [rsp+F0h] [rbp-10h] BYREF
  struct _FLT_RELATED_OBJECTS *v115; // [rsp+F8h] [rbp-8h]
  char v116[8]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v117; // [rsp+108h] [rbp+8h]
  utl::_RefCountBase *v118[2]; // [rsp+118h] [rbp+18h]
  __int64 v119; // [rsp+128h] [rbp+28h]
  int v120; // [rsp+130h] [rbp+30h]
  struct _UNICODE_STRING UnicodeString; // [rsp+140h] [rbp+40h] BYREF
  char v122; // [rsp+150h] [rbp+50h]
  PWSTR *p_Buffer; // [rsp+1B0h] [rbp+B0h]
  _OWORD v124[5]; // [rsp+1C0h] [rbp+C0h] BYREF
  _DWORD v125[20]; // [rsp+210h] [rbp+110h] BYREF

  v8 = 0;
  *a4 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
  v107 = (__int64)a4;
  v114 = a7;
  FileObject = a3->FileObject;
  v115 = a3;
  v11 = FileObject->Flags >> 17;
  v109 = 0;
  v12 = ((v11 & 1) == 0) | 8u;
  *(_OWORD *)v110 = 0;
  v111 = 0;
  LODWORD(v109) = _mm_cvtsi128_si32((__m128i)0LL) | 3;
  v13 = *((_QWORD *)a5 + 1);
  v112 = 0;
  v113 = 0;
  if ( *(_DWORD *)(v13 + 28) == 2 )
    v14 = *(_QWORD *)(*(_QWORD *)(v13 + 32) + 16LL);
  else
    v14 = *((_QWORD *)UnionFs::g_FilterState + 10);
  v95 = a6;
  v15 = UnionFs::UfsPathCache::LookupEntry(v14, a3->Instance, *(_QWORD *)a5, v12, &v109);
  if ( v15 < 0 )
  {
    v16 = "PUSH: Cache lookup";
    v17 = 0x22500020E27LL;
LABEL_30:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v15,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v17,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
      v16,
      (const char *)v95);
    goto LABEL_212;
  }
  v18 = 0;
  v98[0] = 0;
  if ( !DWORD1(v109) )
    goto LABEL_53;
  if ( (BYTE8(v109) & 4) != 0 )
  {
    v19 = -1073741772;
    if ( DWORD1(v109) != 1 )
      v19 = -1073741766;
    if ( (a2->Iopb->Parameters.Create.Options & 1) != 0 )
      MicrosoftTelemetryAssertTriggeredMsgKM("!FlagOn(Cbd.Iopb->Parameters.Create.Options, FILE_DIRECTORY_FILE)");
    a2->IoStatus.Status = v19;
    a2->IoStatus.Information = 0;
    *a4 = FLT_PREOP_COMPLETE;
    goto LABEL_13;
  }
  if ( (_DWORD)v112 == 1 )
  {
    **((_DWORD **)a5 + 20) |= 8u;
LABEL_13:
    v15 = v8;
    goto LABEL_212;
  }
  if ( *((_WORD *)v110[0] + 80) == 4 )
  {
    if ( !*((_QWORD *)v110[0] + 26) )
      MicrosoftTelemetryAssertTriggeredMsgKM("results.CacheEntry->GetOriginalScratchPath()");
    if ( DWORD1(v109) == 1 )
    {
      if ( (a2->Iopb->Parameters.Create.Options & 0x40) == 0 )
        MicrosoftTelemetryAssertTriggeredMsgKM("Failing overwrite on exact match for renamed tombstone");
      v15 = -1073741638;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC00000BALL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x38800020E5FLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
        "ORIGIN: Attempt to overwrite a directory by opening it as a non-directory",
        (const char *)a6);
      goto LABEL_212;
    }
    goto LABEL_49;
  }
  if ( DWORD1(v109) != 1 )
  {
LABEL_49:
    v32 = v111;
    v111 = 0;
    if ( v32 )
    {
      ExReleaseResourceLite(v32);
      KeLeaveCriticalRegion();
    }
    v33 = v110[1];
    v110[1] = 0;
    v110[0] = 0;
    if ( v33 )
      utl::_RefCountBase::_DecStrong(v33);
LABEL_53:
    Context[0] = 0;
    if ( (_DWORD)v112 != 2 )
      goto LABEL_63;
    v34 = (UnionFs::Rtl *)(*(_QWORD *)a5 + 8LL);
    *(_OWORD *)v100 = **((_OWORD **)&v113 + 1);
    *(_OWORD *)Resource = *(_OWORD *)v113;
    v8 = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(
           v34,
           (struct _UNICODE_STRING *)Resource,
           (PCUNICODE_STRING)v100,
           Context,
           (int)a6);
    if ( v8 < 0 )
    {
      v37 = "PUSH: Replacing substring";
      v38 = 0x38300020EDBLL;
LABEL_56:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v8,
        (int)a6,
        (struct UnionFs::StackEventTracer *)v38,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
        v37,
        (const char *)v95);
      v40 = (struct _UNICODE_STRING *)Context[0];
LABEL_57:
      if ( !v40 )
        goto LABEL_13;
      v41 = LOBYTE(v40[1].Length) == 0;
LABEL_59:
      if ( v41 )
        *v40 = 0;
      FsFltWil::Details::FreeUnicodeString(v40, v39);
      ExFreePoolWithTag(v40, 0);
      goto LABEL_13;
    }
    v42 = Context[0];
    if ( !Context[0] )
    {
LABEL_63:
      v8 = UnionFs::UfsPathName::AllocAndInit(*(_QWORD *)a5, Context, a6);
      if ( v8 < 0 )
      {
        v37 = "PUSH: Allocating scratch path for layer lookup";
        v38 = 0x39300020EE6LL;
        goto LABEL_56;
      }
      v42 = Context[0];
    }
    v43 = *((_QWORD *)a5 + 20);
    v44 = *(_QWORD *)(v43 + 64);
    *(_QWORD *)(v43 + 64) = v42;
    if ( v44 )
    {
      if ( !*(_BYTE *)(v44 + 16) )
        *(_OWORD *)v44 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v44, v35);
      ExFreePoolWithTag((PVOID)v44, 0);
    }
    v45 = v110[0];
    v46 = 0;
    Resource[0] = 0;
    v47 = 0;
    P = 0;
    v48 = 0;
    v100[0] = 0;
    if ( v110[0] )
    {
LABEL_137:
      if ( ((*(_BYTE *)(*(_QWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 8) + 20LL) | v18) & 2) != 0 )
      {
        if ( v98[0] )
        {
          if ( (*(_DWORD *)(*((_QWORD *)a5 + 1) + 24LL) & 0x80u) != 0 )
          {
            v98[0] = 0;
            if ( v45 )
            {
              IsFileCowable = UnionFs::Utils::IsFileCowable((UnionFs::Utils *)v98, (bool *)v45, a6, v36);
              v66 = IsFileCowable;
              if ( IsFileCowable < 0 )
              {
                UnionFs::ProcessTraceStatusPushLocation(
                  (UnionFs *)(unsigned int)IsFileCowable,
                  (int)a6,
                  (struct UnionFs::StackEventTracer *)0x78600020F6ALL,
                  (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
                  "PUSH: Checking immutability",
                  (const char *)v95);
LABEL_116:
                if ( v47 )
                  utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v47);
                v69 = (struct _UNICODE_STRING *)P;
                if ( !P )
                  goto LABEL_123;
                v70 = *((_BYTE *)P + 16) == 0;
LABEL_120:
                if ( v70 )
                  *v69 = 0;
                FsFltWil::Details::FreeUnicodeString(v69, v67);
                ExFreePoolWithTag(v69, 0);
LABEL_123:
                v15 = v66;
                goto LABEL_212;
              }
              v45 = v110[0];
              v76 = v98[0];
            }
            else
            {
              v76 = ((unsigned int)v48 & 0x800010) != 0;
            }
            if ( !v76 )
            {
              if ( (unsigned int)dword_14009E178 > 5
                && (qword_14009E188 & 0x400000000000LL) != 0
                && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
              {
                v107 = 1;
                v114 = (struct UnionFs::UfsSiloCtx *)0x1000000;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                  qword_14009E190,
                  (unsigned int)byte_140096135,
                  0,
                  (unsigned int)&v114,
                  (__int64)&v107);
              }
              UnionFs::ProcessTraceStatusOrigin(
                (UnionFs *)0xC0000022LL,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x78700020F7CLL,
                (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
                "ORIGIN: Rejecting COW for immutable file",
                (const char *)v95);
              if ( v47 )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v47);
              v78 = (struct _UNICODE_STRING *)P;
              if ( P )
              {
                if ( !*((_BYTE *)P + 16) )
                  *(_OWORD *)P = 0;
                FsFltWil::Details::FreeUnicodeString(v78, v77);
                ExFreePoolWithTag(v78, 0);
              }
              v15 = -1073741790;
              goto LABEL_212;
            }
          }
          v108 = 1;
          v107 = (__int64)v100;
          *(_OWORD *)v100 = 0;
          if ( v45 )
          {
            if ( v46 || Resource[0] )
            {
              MicrosoftTelemetryAssertTriggeredMsgKM("!layer && !fullPathInLayer");
              v45 = v110[0];
            }
            v79 = (volatile signed __int32 *)*((_QWORD *)v45 + 5);
            v46 = (const struct UnionFs::UfsLayerCtx *)*((_QWORD *)v45 + 4);
            if ( v79 )
            {
              _InterlockedIncrement(v79 + 2);
              v45 = v110[0];
            }
            if ( v47 )
            {
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v47);
              v45 = v110[0];
            }
            v80 = v113;
            Resource[0] = *((PERESOURCE *)v45 + 6);
            Context[0] = *((PFLT_CONTEXT *)a5 + 1);
            v81 = (volatile signed __int32 *)*((_QWORD *)a5 + 2);
            Context[1] = (PFLT_CONTEXT)v81;
            if ( v81 )
              _InterlockedIncrement(v81 + 2);
            v8 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v45, Context, v80, 12, a6);
            if ( v8 < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)v8,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x3F800020FA0LL,
                (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
                "PUSH: ConvertToSoftTombstone for COW",
                (const char *)v95);
              wil::details::lambda_call__lambda_e7ebe5a57b64e075e4cd6400c54e1518___::_lambda_call__lambda_e7ebe5a57b64e075e4cd6400c54e1518___(&v107);
              if ( v100[1] )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v100[1]);
              if ( v79 )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v79);
              v40 = (struct _UNICODE_STRING *)P;
              goto LABEL_57;
            }
            v82 = v110[1];
            v47 = v79;
            v83 = v110[0];
            if ( v110[1] )
              _InterlockedIncrement((volatile signed __int32 *)v110[1] + 2);
            v100[0] = v83;
            v84 = (utl::_RefCountBase *)v100[1];
            v100[1] = v82;
            if ( v84 )
              utl::_RefCountBase::_DecStrong(v84);
            v85 = v111;
            v111 = 0;
            if ( v85 )
            {
              ExReleaseResourceLite(v85);
              KeLeaveCriticalRegion();
            }
          }
          v86 = v115;
          v66 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
                  *((UnionFs::UfsUnionCtx **)a5 + 1),
                  a2,
                  v115,
                  *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
                  *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
                  *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
                  v46,
                  a6,
                  v114);
          if ( v66 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v66,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x29500020FB2LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
              "PUSH: Preparing for COW",
              (const char *)v96);
            wil::details::lambda_call__lambda_e7ebe5a57b64e075e4cd6400c54e1518___::_lambda_call__lambda_e7ebe5a57b64e075e4cd6400c54e1518___(&v107);
            if ( v100[1] )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v100[1]);
            goto LABEL_116;
          }
          v87 = v110[0];
          *(_QWORD *)v116 = *((_QWORD *)a5 + 1);
          v88 = v110[1];
          v119 = 0;
          v120 = 22;
          v117 = 0;
          *(_OWORD *)v118 = 0;
          if ( v110[1] )
            _InterlockedIncrement((volatile signed __int32 *)v110[1] + 2);
          *((_QWORD *)&v117 + 1) = v87;
          v89 = v118[0];
          v118[0] = v88;
          if ( v89 )
            utl::_RefCountBase::_DecStrong(v89);
          UnionFs::UfsPathName::UfsPathName(
            (UnionFs::UfsPathName *)&UnicodeString,
            (const struct _UNICODE_STRING *)(*(_QWORD *)a5 + 8LL),
            *(_WORD *)(*(_QWORD *)a5 + 24LL));
          v66 = UnionFs::Utils::CopyItem(
                  (_DWORD)a2,
                  (_DWORD)v46,
                  Resource[0],
                  v86->Instance,
                  &UnicodeString,
                  (__int64)v116,
                  (struct _FILE_OBJECT *)a6,
                  0);
          if ( v66 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v66,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x29200020FC3LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
              "PUSH: Performing COW",
              (const char *)v97);
            if ( !v122 )
              UnicodeString = 0;
            FsFltWil::Details::FreeUnicodeString(&UnicodeString, v91);
            if ( v118[0] )
              utl::_RefCountBase::_DecStrong(v118[0]);
            wil::details::lambda_call__lambda_e7ebe5a57b64e075e4cd6400c54e1518___::_lambda_call__lambda_e7ebe5a57b64e075e4cd6400c54e1518___(&v107);
            if ( v100[1] )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v100[1]);
            if ( v47 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v47);
            v69 = (struct _UNICODE_STRING *)P;
            if ( !P )
              goto LABEL_123;
            v70 = *((_BYTE *)P + 16) == 0;
            goto LABEL_120;
          }
          v108 = 0;
          if ( !v122 )
            UnicodeString = 0;
          FsFltWil::Details::FreeUnicodeString(&UnicodeString, v90);
          if ( v118[0] )
            utl::_RefCountBase::_DecStrong(v118[0]);
          wil::details::lambda_call__lambda_e7ebe5a57b64e075e4cd6400c54e1518___::_lambda_call__lambda_e7ebe5a57b64e075e4cd6400c54e1518___(&v107);
          if ( v100[1] )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v100[1]);
        }
      }
      else
      {
        v92 = (_DWORD *)v107;
        a2->IoStatus.Status = -1073741790;
        a2->IoStatus.Information = 0;
        *v92 = 4;
      }
LABEL_205:
      if ( v47 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v47);
      v93 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v93, v48);
        ExFreePoolWithTag(v93, 0);
      }
      v15 = 0;
      goto LABEL_212;
    }
    UnicodeString.Buffer = (PWSTR)off_14007E740;
    p_Buffer = &UnicodeString.Buffer;
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(a6, &UnicodeString);
    memset(v124, 0, 0x48u);
    v95 = a6;
    v50 = UnionFs::Utils::StatItemAsCaller(*(_QWORD *)a5 + 8LL, v115->Instance, v49, v124, a2);
    v51 = *((_WORD *)a6 + 245);
    if ( v51 )
    {
      v52 = v51 - 1;
      *((_WORD *)a6 + 245) = v52;
      v53 = 120 * (v52 + 1LL);
      v48 = *(struct _UNICODE_STRING **)((char *)a6 + v53);
      *(_QWORD *)((char *)a6 + v53) = 0;
      if ( v48 )
        (*(void (__fastcall **)(struct _UNICODE_STRING *))(*(_QWORD *)&v48->Length + 24LL))(v48);
    }
    if ( v50 == 260 )
      goto LABEL_102;
    v54 = -1073741772;
    if ( v50 != -1073741766 )
    {
      if ( v50 >= 0 )
      {
        v48 = 0;
LABEL_136:
        v18 = BYTE4(v124[4]);
        v45 = v110[0];
        v46 = (const struct UnionFs::UfsLayerCtx *)v100[0];
        goto LABEL_137;
      }
      if ( v50 != -1073741772 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v50,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0xF700020F0BLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
          "PUSH: Querying stat information",
          (const char *)a6);
        v56 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v56, v55);
          ExFreePoolWithTag(v56, 0);
        }
        v15 = v50;
        goto LABEL_212;
      }
    }
    utl::make_unique<UnionFs::FindAndStatResults,,0>(v100);
    v57 = (unsigned __int16 *)v100[0];
    if ( !v100[0] )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x40000020F16LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
        "ORIGIN: Allocating findAndStatResults",
        (const char *)a6);
      v59 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v59, v58);
        ExFreePoolWithTag(v59, 0);
      }
      v15 = -1073741670;
      goto LABEL_212;
    }
    *((_QWORD *)v100[0] + 12) = &P;
    v60 = *((_QWORD *)a5 + 1);
    v95 = (struct UnionFs::UfsStreamHandleCtx *)v57;
    *(_OWORD *)v100 = *(_OWORD *)*(_QWORD *)(*((_QWORD *)a5 + 20) + 64LL);
    v61 = UnionFs::UfsUnionCtx::FindAndStatItemInLayersAsCaller(v60, a2, v100);
    v8 = v61;
    if ( v61 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v61,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0xF800020F21LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
        "PUSH: Probing for item in layers",
        (const char *)v57);
      if ( v57 )
      {
        v62 = (utl::_RefCountBase *)*((_QWORD *)v57 + 11);
        if ( v62 )
          utl::_RefCountBase::_DecStrong(v62);
        ExFreePoolWithTag(v57, 0);
      }
      v40 = (struct _UNICODE_STRING *)P;
      if ( !P )
        goto LABEL_13;
      v41 = *((_BYTE *)P + 16) == 0;
      goto LABEL_59;
    }
    if ( v61 == 260 )
    {
      if ( v57 )
      {
        v63 = (utl::_RefCountBase *)*((_QWORD *)v57 + 11);
        if ( v63 )
          utl::_RefCountBase::_DecStrong(v63);
        ExFreePoolWithTag(v57, 0);
      }
LABEL_102:
      v64 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v64, v48);
        ExFreePoolWithTag(v64, 0);
      }
      v15 = 260;
      goto LABEL_212;
    }
    v124[0] = *(_OWORD *)(v57 + 4);
    v124[1] = *(_OWORD *)(v57 + 12);
    v124[2] = *(_OWORD *)(v57 + 20);
    v124[3] = *(_OWORD *)(v57 + 28);
    *(_QWORD *)&v124[4] = *((_QWORD *)v57 + 9);
    v47 = (volatile signed __int32 *)*((_QWORD *)v57 + 11);
    v100[0] = *((PVOID *)v57 + 10);
    if ( v47 )
      _InterlockedIncrement(v47 + 2);
    v65 = *v57;
    if ( (_WORD)v65 != 1 )
    {
      if ( v65 == 2 )
      {
        v71 = -1073741766;
        if ( v50 == -1073741772 )
          v71 = -1073741772;
        v54 = v71;
      }
      else if ( v65 != 3 )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("false");
        v66 = -1073741595;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000E5LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x60C00020F42LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
          "ORIGIN: Unexpected LAYER_FIND_RESULT",
          (const char *)v57);
        if ( v57 )
        {
          v68 = (utl::_RefCountBase *)*((_QWORD *)v57 + 11);
          if ( v68 )
            utl::_RefCountBase::_DecStrong(v68);
          ExFreePoolWithTag(v57, 0);
        }
        goto LABEL_116;
      }
      v72 = (_DWORD *)v107;
      a2->IoStatus.Status = v54;
      a2->IoStatus.Information = 0;
      *v72 = 4;
      if ( v57 )
      {
        v73 = (utl::_RefCountBase *)*((_QWORD *)v57 + 11);
        if ( v73 )
          utl::_RefCountBase::_DecStrong(v73);
        ExFreePoolWithTag(v57, 0);
      }
      goto LABEL_205;
    }
    v48 = (struct _UNICODE_STRING *)*((unsigned int *)v57 + 16);
    Resource[0] = (PERESOURCE)P;
    v98[0] = 1;
    LODWORD(Context[0]) = (_DWORD)v48;
    if ( v57 )
    {
      v74 = (utl::_RefCountBase *)*((_QWORD *)v57 + 11);
      if ( v74 )
        utl::_RefCountBase::_DecStrong(v74);
      ExFreePoolWithTag(v57, 0);
      v48 = (struct _UNICODE_STRING *)LODWORD(Context[0]);
    }
    goto LABEL_136;
  }
  memset(v125, 0, 0x48u);
  HostSilo = (unsigned int *)PsGetHostSilo(v21, v20);
  v23 = v110[0];
  v24 = (volatile signed __int32 *)*((_QWORD *)v110[0] + 5);
  v25 = *((_QWORD *)v110[0] + 4);
  if ( v24 )
  {
    _InterlockedIncrement(v24 + 2);
    v23 = v110[0];
  }
  v26 = **(_QWORD **)(v25 + 8);
  *(_OWORD *)v100 = *(_OWORD *)*((_QWORD *)v23 + 6);
  v15 = UnionFs::Utils::StatItemAsCaller(
          (const char *)v100,
          v26,
          HostSilo,
          4,
          (__int64)v125,
          (UnionFs::Utils *)a2,
          (int)a6);
  if ( v24 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v24);
  v8 = 0;
  if ( v15 < 0 )
  {
    v16 = "PUSH: Stat layer item";
    v17 = 0x22600020E79LL;
    goto LABEL_30;
  }
  if ( v15 == 260 )
  {
    v15 = 260;
    goto LABEL_212;
  }
  v27 = v110[0];
  v18 = v125[17];
  FltReferenceContext(*((PFLT_CONTEXT *)v110[0] + 9));
  Context[0] = *((PFLT_CONTEXT *)v27 + 9);
  v28 = (struct UnionFs::UfsStreamHandleCtx *)*((_QWORD *)Context[0] + 4);
  FsFltWil::AcquireResourceExclusive(Resource, *((_QWORD *)v28 + 15) + 56LL);
  SecurityContext = a2->Iopb->Parameters.Create.SecurityContext;
  v102 = 0;
  BYTE4(v100[1]) = 1;
  AccessState = SecurityContext->AccessState;
  v101 = 10;
  v98[0] = 0;
  LODWORD(SecurityContext) = AccessState->OriginalDesiredAccess;
  *(_WORD *)((char *)&v100[1] + 5) = 0;
  v31 = (unsigned int)SecurityContext | 2;
  HIBYTE(v100[1]) = 0;
  v103 = 0;
  v104 = 0;
  v95 = v28;
  v100[0] = (PVOID)((unsigned int)v31 | 0x900000000LL);
  LODWORD(v100[1]) = v31;
  v15 = UnionFs::UnionFsFilter::CheckOplockAndShareAccess(v31, a2, v115, Context, v100);
  if ( v15 >= 0 )
  {
    if ( v15 == 259 )
    {
      *a4 = FLT_PREOP_PENDING;
      if ( Resource[0] )
      {
        ExReleaseResourceLite(Resource[0]);
        KeLeaveCriticalRegion();
      }
      if ( Context[0] )
        FltReleaseContext(Context[0]);
      goto LABEL_13;
    }
    v98[0] = 1;
    if ( Resource[0] )
    {
      ExReleaseResourceLite(Resource[0]);
      KeLeaveCriticalRegion();
    }
    if ( Context[0] )
      FltReleaseContext(Context[0]);
    goto LABEL_53;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v15,
    (int)a6,
    (struct UnionFs::StackEventTracer *)0x6E600020EA9LL,
    (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwrite",
    "PUSH: Oplock and share access check",
    (const char *)v95);
  if ( Resource[0] )
  {
    ExReleaseResourceLite(Resource[0]);
    KeLeaveCriticalRegion();
  }
  if ( Context[0] )
    FltReleaseContext(Context[0]);
LABEL_212:
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v109);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140017370  mov     [rsp-8+arg_0], rbx
0x140017375  push    rbp
0x140017376  push    rsi
0x140017377  push    rdi
0x140017378  push    r12
0x14001737a  push    r13
0x14001737c  push    r14
0x14001737e  push    r15
0x140017380  lea     rbp, [rsp-170h]
0x140017388  sub     rsp, 270h
0x14001738f  mov     rax, cs:__security_cookie
0x140017396  xor     rax, rsp
0x140017399  mov     [rbp+1A0h+var_40], rax
0x1400173a0  mov     rax, [rbp+1A0h+arg_30]
0x1400173a7  mov     r12, r9
0x1400173aa  mov     r13, [rbp+1A0h+arg_20]
0x1400173b1  xor     edi, edi
0x1400173b3  mov     rsi, [rbp+1A0h+arg_28]
0x1400173ba  xorps   xmm1, xmm1
0x1400173bd  mov     [r9], edi
0x1400173c0  xorps   xmm0, xmm0
0x1400173c3  mov     [rbp+1A0h+var_208], r9
0x1400173c7  mov     r10, r8
0x1400173ca  mov     [rbp+1A0h+var_1B0], rax
0x1400173ce  mov     r15, rdx
0x1400173d1  mov     rax, [r8+20h]
0x1400173d5  mov     [rbp+1A0h+var_1A8], r8
0x1400173d9  mov     r9d, [rax+50h]
0x1400173dd  shr     r9d, 11h
0x1400173e1  movd    eax, xmm1
0x1400173e5  not     r9d
0x1400173e8  movdqa  [rbp+1A0h+var_1F0], xmm1
0x1400173ed  and     r9d, 1
0x1400173f1  or      r9d, 8
0x1400173f5  movdqa  xmmword ptr [rbp+1A0h+var_1E0], xmm0
0x1400173fa  or      eax, 3
0x1400173fd  mov     [rbp+1A0h+var_1D0], rdi
0x140017401  mov     dword ptr [rbp+1A0h+var_1F0], eax
0x140017404  mov     rax, [r13+8]
0x140017408  mov     [rbp+1A0h+var_1C8], rdi
0x14001740c  movdqa  [rbp+1A0h+var_1C0], xmm0
0x140017411  cmp     dword ptr [rax+1Ch], 2
0x140017415  jnz     short loc_140017421
0x140017417  mov     rax, [rax+20h]
0x14001741b  mov     rcx, [rax+10h]
0x14001741f  jmp     short loc_14001742C
0x140017421  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140017428  mov     rcx, [rax+50h]
0x14001742c  mov     r8, [r13+0]
0x140017430  lea     rax, [rbp+1A0h+var_1F0]
0x140017434  mov     rdx, [r10+18h]
0x140017438  mov     [rsp+2A0h+var_270], r15
0x14001743d  mov     [rsp+2A0h+var_278], rsi; char *
0x140017442  mov     [rsp+2A0h+var_280], rax
0x140017447  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x14001744c  mov     ebx, eax
0x14001744e  test    eax, eax
0x140017450  jns     short loc_140017468
0x140017452  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x140017459  mov     r8, 22500020E27h
0x140017463  jmp     loc_1400175FC
0x140017468  mov     ecx, dword ptr [rbp+1A0h+var_1F0+4]
0x14001746b  mov     r14d, edi
0x14001746e  mov     [rsp+2A0h+var_250], dil
0x140017473  mov     edx, 4
0x140017478  test    ecx, ecx
0x14001747a  jz      loc_140017820
0x140017480  test    byte ptr [rbp+1A0h+var_1F0+8], dl
0x140017483  jz      short loc_1400174C7
0x140017485  mov     eax, 0C000003Ah
0x14001748a  mov     edx, 1
0x14001748f  cmp     ecx, edx
0x140017491  lea     r14d, [rax-6]
0x140017495  cmovnz  r14d, eax
0x140017499  mov     rax, [r15+10h]
0x14001749d  mov     ecx, [rax+20h]
0x1400174a0  test    dl, cl
0x1400174a2  jz      short loc_1400174B0
0x1400174a4  lea     rcx, aFlagonCbdIopbP; "!FlagOn(Cbd.Iopb->Parameters.Create.Opt"...
0x1400174ab  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400174b0  mov     [r15+18h], r14d
0x1400174b4  mov     [r15+20h], rdi
0x1400174b8  mov     dword ptr [r12], 4
0x1400174c0  mov     ebx, edi
0x1400174c2  jmp     loc_140018310
0x1400174c7  mov     ebx, 1
0x1400174cc  cmp     dword ptr [rbp+1A0h+var_1C8], ebx
0x1400174cf  jnz     short loc_1400174DD
0x1400174d1  mov     rax, [r13+0A0h]
0x1400174d8  or      dword ptr [rax], 8
0x1400174db  jmp     short loc_1400174C0
0x1400174dd  mov     rax, [rbp+1A0h+var_1E0]
0x1400174e1  movzx   ecx, word ptr [rax+0A0h]
0x1400174e8  nop
0x1400174e9  cmp     cx, dx
0x1400174ec  jnz     short loc_140017559
0x1400174ee  mov     rax, [rbp+1A0h+var_1E0]
0x1400174f2  cmp     [rax+0D0h], rdi
0x1400174f9  jnz     short loc_140017507
0x1400174fb  lea     rcx, aResultsCacheen; "results.CacheEntry->GetOriginalScratchP"...
0x140017502  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140017507  cmp     dword ptr [rbp+1A0h+var_1F0+4], ebx
0x14001750a  jnz     loc_1400177E5
0x140017510  mov     rax, [r15+10h]
0x140017514  mov     ecx, [rax+20h]
0x140017517  test    cl, 40h
0x14001751a  jnz     short loc_140017528
0x14001751c  lea     rcx, aFailingOverwri; "Failing overwrite on exact match for re"...
0x140017523  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140017528  lea     rax, aOriginAttemptT_2; "ORIGIN: Attempt to overwrite a director"...
0x14001752f  mov     ebx, 0C00000BAh
0x140017534  mov     ecx, ebx; this
0x140017536  mov     [rsp+2A0h+var_280], rax; char *
0x14001753b  lea     r9, aUnionfsUnionfs_43; "UnionFs::UnionFsFilter::PreCreateFileOv"...
0x140017542  mov     r8, 38800020E5Fh; struct UnionFs::StackEventTracer *
0x14001754c  mov     rdx, rsi; int
0x14001754f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140017554  jmp     loc_140018310
0x140017559  cmp     dword ptr [rbp+1A0h+var_1F0+4], ebx
0x14001755c  jnz     loc_1400177E5
0x140017562  xor     edx, edx; Val
0x140017564  lea     rcx, [rbp+1A0h+var_90]; void *
0x14001756b  lea     r8d, [rdx+48h]; Size
0x14001756f  call    memset
0x140017574  call    cs:__imp_PsGetHostSilo
0x14001757b  nop     dword ptr [rax+rax+00h]
0x140017580  mov     r8, rax
0x140017583  mov     rax, [rbp+1A0h+var_1E0]
0x140017587  mov     rdi, [rax+28h]
0x14001758b  mov     rcx, [rax+20h]
0x14001758f  test    rdi, rdi
0x140017592  jz      short loc_14001759C
0x140017594  lock inc dword ptr [rdi+8]
0x140017598  mov     rax, [rbp+1A0h+var_1E0]
0x14001759c  mov     rax, [rax+30h]
0x1400175a0  mov     r9d, 4
0x1400175a6  mov     rcx, [rcx+8]
0x1400175aa  mov     [rsp+2A0h+var_270], rsi
0x1400175af  mov     [rsp+2A0h+var_278], r15; char *
0x1400175b4  movups  xmm0, xmmword ptr [rax]
0x1400175b7  mov     rdx, [rcx]
0x1400175ba  lea     rax, [rbp+1A0h+var_90]
0x1400175c1  lea     rcx, [rsp+2A0h+var_240]
0x1400175c6  mov     [rsp+2A0h+var_280], rax
0x1400175cb  movdqu  xmmword ptr [rsp+2A0h+var_240], xmm0
0x1400175d1  call    ?StatItemAsCaller@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::StatItemAsCaller(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x1400175d6  mov     ebx, eax
0x1400175d8  test    rdi, rdi
0x1400175db  jz      short loc_1400175E5
0x1400175dd  mov     rcx, rdi; this
0x1400175e0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400175e5  xor     edi, edi
0x1400175e7  test    ebx, ebx
0x1400175e9  jns     short loc_140017617
0x1400175eb  lea     rax, aPushStatLayerI; "PUSH: Stat layer item"
0x1400175f2  mov     r8, 22600020E79h; struct UnionFs::StackEventTracer *
0x1400175fc  lea     r9, aUnionfsUnionfs_43; "UnionFs::UnionFsFilter::PreCreateFileOv"...
0x140017603  mov     [rsp+2A0h+var_280], rax; char *
0x140017608  mov     rdx, rsi; int
0x14001760b  mov     ecx, ebx; this
0x14001760d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140017612  jmp     loc_140018310
0x140017617  mov     eax, 104h
0x14001761c  cmp     ebx, eax
0x14001761e  jnz     short loc_140017627
0x140017620  mov     ebx, eax
0x140017622  jmp     loc_140018310
0x140017627  mov     rbx, [rbp+1A0h+var_1E0]
0x14001762b  mov     r14d, [rbp+1A0h+var_4C]
0x140017632  mov     rcx, [rbx+48h]; Context
0x140017636  call    cs:__imp_FltReferenceContext
0x14001763d  nop     dword ptr [rax+rax+00h]
0x140017642  mov     rax, [rbx+48h]
0x140017646  lea     rcx, [rbp+1A0h+Resource]
0x14001764a  mov     [rsp+2A0h+Context], rax
0x14001764f  mov     rbx, [rax+20h]
0x140017653  mov     rdx, [rbx+78h]
0x140017657  add     rdx, 38h ; '8'
0x14001765b  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140017660  mov     rax, [r15+10h]
0x140017664  lea     r9, [rsp+2A0h+Context]
0x140017669  mov     r8, [rbp+1A0h+var_1A8]
0x14001766d  mov     rdx, r15
0x140017670  mov     [rsp+2A0h+var_260], rsi
0x140017675  mov     [rsp+2A0h+var_268], r13
0x14001767a  mov     rcx, [rax+18h]
0x14001767e  mov     [rsp+2A0h+var_22C], dil
0x140017683  mov     dword ptr [rsp+2A0h+var_240+4], 9
0x14001768b  mov     byte ptr [rsp+2A0h+var_240+0Ch], 1
0x140017690  mov     rax, [rcx+8]
0x140017694  mov     [rsp+2A0h+var_230], 0Ah
0x14001769c  mov     [rsp+2A0h+var_250], dil
0x1400176a1  mov     ecx, [rax+18h]
0x1400176a4  xor     eax, eax
0x1400176a6  mov     word ptr [rsp+2A0h+var_240+0Dh], ax
0x1400176ab  or      ecx, 2
0x1400176ae  mov     byte ptr [rsp+2A0h+var_240+0Fh], al
0x1400176b2  mov     [rsp+2A0h+var_22B], ax
0x1400176b7  mov     [rsp+2A0h+var_229], al
0x1400176bb  lea     rax, [rsp+2A0h+var_250]
0x1400176c0  mov     [rsp+2A0h+var_270], rax
0x1400176c5  lea     rax, [rsp+2A0h+var_240]
0x1400176ca  mov     [rsp+2A0h+var_278], rbx; char *
0x1400176cf  mov     [rsp+2A0h+var_280], rax
0x1400176d4  mov     dword ptr [rsp+2A0h+var_240], ecx
0x1400176d8  mov     dword ptr [rsp+2A0h+var_240+8], ecx
0x1400176dc  call    ?CheckOplockAndShareAccess@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@$$QEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBUCheckOplockAndShareAccessParams@12@AEAVUfsFsContext@2@PEA_NAEAUCreateContext@2@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::CheckOplockAndShareAccess(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &&,UnionFs::UnionFsFilter::CheckOplockAndShareAccessParams const &,UnionFs::UfsFsContext &,bool *,UnionFs::CreateContext &,UnionFs::StackEventTracer &)
0x1400176e1  mov     ebx, eax
0x1400176e3  test    eax, eax
0x1400176e5  jns     short loc_14001774E
0x1400176e7  lea     rax, aPushOplockAndS; "PUSH: Oplock and share access check"
0x1400176ee  mov     r8, 6E600020EA9h; struct UnionFs::StackEventTracer *
0x1400176f8  lea     r9, aUnionfsUnionfs_43; "UnionFs::UnionFsFilter::PreCreateFileOv"...
0x1400176ff  mov     [rsp+2A0h+var_280], rax; char *
0x140017704  mov     rdx, rsi; int
0x140017707  mov     ecx, ebx; this
0x140017709  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001770e  mov     rcx, [rbp+1A0h+Resource]; Resource
0x140017712  test    rcx, rcx
0x140017715  jz      short loc_14001772F
0x140017717  call    cs:__imp_ExReleaseResourceLite
0x14001771e  nop     dword ptr [rax+rax+00h]
0x140017723  call    cs:__imp_KeLeaveCriticalRegion
0x14001772a  nop     dword ptr [rax+rax+00h]
0x14001772f  mov     rcx, [rsp+2A0h+Context]; Context
0x140017734  test    rcx, rcx
0x140017737  jz      loc_140018310
0x14001773d  call    cs:__imp_FltReleaseContext
0x140017744  nop     dword ptr [rax+rax+00h]
0x140017749  jmp     loc_140018310
0x14001774e  cmp     ebx, 103h
0x140017754  jnz     short loc_140017760
0x140017756  mov     dword ptr [r12], 2
0x14001775e  jmp     short loc_140017767
0x140017760  cmp     [rsp+2A0h+var_250], dil
0x140017765  jz      short loc_1400177A7
0x140017767  mov     rcx, [rbp+1A0h+Resource]; Resource
0x14001776b  test    rcx, rcx
0x14001776e  jz      short loc_140017788
0x140017770  call    cs:__imp_ExReleaseResourceLite
0x140017777  nop     dword ptr [rax+rax+00h]
0x14001777c  call    cs:__imp_KeLeaveCriticalRegion
0x140017783  nop     dword ptr [rax+rax+00h]
0x140017788  mov     rcx, [rsp+2A0h+Context]; Context
0x14001778d  test    rcx, rcx
0x140017790  jz      loc_1400174C0
0x140017796  call    cs:__imp_FltReleaseContext
0x14001779d  nop     dword ptr [rax+rax+00h]
0x1400177a2  jmp     loc_1400174C0
0x1400177a7  mov     rcx, [rbp+1A0h+Resource]; Resource
0x1400177ab  mov     [rsp+2A0h+var_250], 1
0x1400177b0  test    rcx, rcx
0x1400177b3  jz      short loc_1400177CD
0x1400177b5  call    cs:__imp_ExReleaseResourceLite
0x1400177bc  nop     dword ptr [rax+rax+00h]
0x1400177c1  call    cs:__imp_KeLeaveCriticalRegion
0x1400177c8  nop     dword ptr [rax+rax+00h]
0x1400177cd  mov     rcx, [rsp+2A0h+Context]; Context
0x1400177d2  test    rcx, rcx
0x1400177d5  jz      short loc_140017820
0x1400177d7  call    cs:__imp_FltReleaseContext
0x1400177de  nop     dword ptr [rax+rax+00h]
0x1400177e3  jmp     short loc_140017820
0x1400177e5  mov     rcx, [rbp+1A0h+var_1D0]; Resource
0x1400177e9  mov     [rbp+1A0h+var_1D0], rdi
0x1400177ed  test    rcx, rcx
0x1400177f0  jz      short loc_14001780A
0x1400177f2  call    cs:__imp_ExReleaseResourceLite
0x1400177f9  nop     dword ptr [rax+rax+00h]
0x1400177fe  call    cs:__imp_KeLeaveCriticalRegion
0x140017805  nop     dword ptr [rax+rax+00h]
0x14001780a  mov     rcx, [rbp+1A0h+var_1E0+8]; this
0x14001780e  mov     [rbp+1A0h+var_1E0+8], rdi
0x140017812  mov     [rbp+1A0h+var_1E0], rdi
0x140017816  test    rcx, rcx
0x140017819  jz      short loc_140017820
0x14001781b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140017820  cmp     dword ptr [rbp+1A0h+var_1C8], 2
0x140017824  mov     [rsp+2A0h+Context], rdi
0x140017829  jnz     loc_1400178E7
0x14001782f  mov     rax, qword ptr [rbp+1A0h+var_1C0+8]
0x140017833  lea     r8, [rsp+2A0h+var_240]; Source
0x140017838  mov     rcx, [r13+0]
0x14001783c  lea     rdx, [rbp+1A0h+Resource]; struct _UNICODE_STRING *
0x140017840  add     rcx, 8; this
0x140017844  mov     [rsp+2A0h+var_278], rsi; char *
0x140017849  movzx   r9d, word ptr [rax+18h]
0x14001784e  movups  xmm0, xmmword ptr [rax]
0x140017851  mov     rax, qword ptr [rbp+1A0h+var_1C0]
0x140017855  movdqu  xmmword ptr [rsp+2A0h+var_240], xmm0
0x14001785b  movups  xmm1, xmmword ptr [rax]
0x14001785e  lea     rax, [rsp+2A0h+Context]
0x140017863  mov     [rsp+2A0h+var_280], rax; P
0x140017868  movdqu  xmmword ptr [rbp+1A0h+Resource], xmm1
0x14001786d  call    ?AllocAndInitWithReplacedPathPrefix@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@00GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140017872  xor     r8d, r8d
0x140017875  mov     edi, eax
0x140017877  test    eax, eax
0x140017879  jns     short loc_1400178DD
0x14001787b  lea     rax, aPushReplacingS_3; "PUSH: Replacing substring"
  ... truncated ...
```
