# UnionFs::UnionFsFilter::PreCreateFileSupersede(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x140019438`
- end: `0x14001a103`
- name: `?PreCreateFileSupersede@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `3275`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x140011e00`

## callees

- `0x14000110c`
- `0x14000efd0`
- `0x14000f7fc`
- `0x140010b88`
- `0x140010e5c`
- `0x140011198`
- `0x1400114c4`
- `0x140019438`
- `0x14003cd88`
- `0x1400419a8`
- `0x1400424ec`
- `0x1400430fc`
- `0x14004397c`
- `0x140043ef4`
- `0x140056ac4`
- `0x140056afc`
- `0x140060ed8`
- `0x1400610fc`
- `0x140077f94`
- `0x140078304`
- `0x140079a6c`
- `0x140079c48`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400199b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019c4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019d03`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019dc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400199b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019c4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019d03`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019dc3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e17`
- `ntoskrnl!PsGetHostSilo` at `0x1400196a1`
- `ntoskrnl!PsGetHostSilo` at `0x1400196a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019845`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400198a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400198dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019f34`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019845`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400198a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400198dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019f34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019851`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400198ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400198e8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019f40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019851`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400198ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400198e8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019f40`
- `FLTMGR!FltReferenceContext` at `0x140019769`
- `FLTMGR!FltReferenceContext` at `0x140019769`
- `FLTMGR!FltReleaseContext` at `0x14001986a`
- `FLTMGR!FltReleaseContext` at `0x1400198c1`
- `FLTMGR!FltReleaseContext` at `0x14001986a`
- `FLTMGR!FltReleaseContext` at `0x1400198c1`

## string_xrefs

- `0x14001a03a`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x14001951a`: `PUSH: Cache lookup`
- `0x14001960c`: `results.CacheEntry->GetOriginalScratchPath()`
- `0x1400199e6`: `PUSH: Allocating scratch path for layer lookup`
- `0x14001952b`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x14001964d`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x14001970c`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019825`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019976`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019b8b`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019bf0`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019d9a`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019ed3`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x14001a04a`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019578`: `!FlagOn(Cbd.Iopb->Parameters.Create.Options, FILE_DIRECTORY_FILE)`
- `0x14001962e`: `Failing supersede on exact match for renamed tombstone`
- `0x14001963a`: `ORIGIN: Attempt to supersede a directory by opening it as a non-directory`
- `0x140019814`: `PUSH: Oplock and share access check`
- `0x140019d84`: `PUSH: Preparing for scratch create`
- `0x140019f93`: `PUSH: Preparing for scratch create`
- `0x14001a051`: `Caller does not have DELETE access`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCreateFileSupersede(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        enum _FLT_PREOP_CALLBACK_STATUS *a4,
        struct UnionFs::CreateContext *a5,
        struct UnionFs::StackEventTracer *a6,
        const struct UnionFs::UfsSiloCtx *a7)
{
  volatile signed __int32 *v8; // rdi
  PFILE_OBJECT FileObject; // rax
  ULONG v11; // r9d
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // ebx
  utl::_RefCountBase *v16; // rax
  int v17; // r15d
  utl::_RefCountBase *v18; // rcx
  utl::_RefCountBase *v19; // rcx
  _QWORD **v20; // r12
  __int64 v21; // rdx
  __int64 v22; // rcx
  unsigned int *HostSilo; // rax
  __int64 v24; // rdx
  const char *v25; // rax
  __int64 v26; // r8
  utl::_RefCountBase *v27; // rbx
  struct UnionFs::UfsStreamHandleCtx *v28; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _FLT_RELATED_OBJECTS *v30; // r12
  __int64 v31; // rcx
  struct _ERESOURCE *v32; // rcx
  utl::_RefCountBase *v33; // rcx
  UnionFs::Rtl *v34; // rcx
  struct _UNICODE_STRING *v35; // rdx
  int v36; // r9d
  const char *v37; // rax
  __int64 v38; // r8
  struct _UNICODE_STRING *v39; // rdx
  char *v40; // rbx
  PFLT_CONTEXT v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rbx
  UnionFs::UfsPathCachePayload *v44; // rbx
  int v45; // r8d
  char v46; // dl
  char v47; // r12
  __int64 v48; // r8
  __int16 v49; // ax
  unsigned __int16 v50; // ax
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rcx
  int v54; // eax
  utl::_RefCountBase *v55; // rcx
  utl::_RefCountBase *v56; // rcx
  volatile signed __int32 *v57; // r15
  PVOID v58; // rcx
  __int16 v59; // ax
  utl::_RefCountBase *v60; // rax
  utl::_RefCountBase *v61; // rcx
  int v62; // eax
  int v63; // edi
  utl::_RefCountBase *v64; // rcx
  utl::_RefCountBase *v65; // rcx
  __int64 v66; // r8
  volatile signed __int32 *v67; // rax
  utl::_RefCountBase *v68; // rax
  utl::_RefCountBase *v69; // rcx
  utl::_RefCountBase *v70; // rcx
  struct _ERESOURCE *v71; // rcx
  int v72; // eax
  utl::_RefCountBase *v73; // rax
  struct UnionFs::UfsStreamHandleCtx *v75; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v76; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v77; // [rsp+28h] [rbp-D8h]
  struct _FLT_RELATED_OBJECTS *v78; // [rsp+58h] [rbp-A8h] BYREF
  int v79; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P; // [rsp+68h] [rbp-98h] BYREF
  PERESOURCE Resource[2]; // [rsp+70h] [rbp-90h] BYREF
  PFLT_CONTEXT Context[2]; // [rsp+80h] [rbp-80h] BYREF
  struct UnionFs::UfsSiloCtx *v83; // [rsp+90h] [rbp-70h] BYREF
  utl::_RefCountBase *v84[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v85; // [rsp+B0h] [rbp-50h] BYREF
  utl::_RefCountBase *v86[2]; // [rsp+C0h] [rbp-40h]
  PERESOURCE v87; // [rsp+D0h] [rbp-30h]
  __int64 v88; // [rsp+D8h] [rbp-28h]
  __int128 v89; // [rsp+E0h] [rbp-20h]
  struct _UNICODE_STRING v90; // [rsp+F0h] [rbp-10h] BYREF
  int v91; // [rsp+100h] [rbp+0h]
  char v92; // [rsp+104h] [rbp+4h]
  __int16 v93; // [rsp+105h] [rbp+5h]
  char v94; // [rsp+107h] [rbp+7h]
  char v95[8]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v96[14]; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v97[5]; // [rsp+180h] [rbp+80h] BYREF
  _DWORD v98[20]; // [rsp+1D0h] [rbp+D0h] BYREF

  v8 = 0;
  *a4 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
  v84[0] = (utl::_RefCountBase *)a4;
  v83 = a7;
  FileObject = a3->FileObject;
  v78 = a3;
  v11 = FileObject->Flags >> 17;
  v85 = 0;
  v12 = ((v11 & 1) == 0) | 8u;
  *(_OWORD *)v86 = 0;
  v87 = 0;
  LODWORD(v85) = _mm_cvtsi128_si32((__m128i)0LL) | 3;
  v13 = *((_QWORD *)a5 + 1);
  v88 = 0;
  v89 = 0;
  if ( *(_DWORD *)(v13 + 28) == 2 )
    v14 = *(_QWORD *)(*(_QWORD *)(v13 + 32) + 16LL);
  else
    v14 = *((_QWORD *)UnionFs::g_FilterState + 10);
  v75 = a6;
  v15 = UnionFs::UfsPathCache::LookupEntry(v14, a3->Instance, *(_QWORD *)a5, v12, &v85);
  if ( v15 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v15,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x22000020581LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
      "PUSH: Cache lookup",
      (const char *)a6);
    goto LABEL_161;
  }
  v15 = 0;
  P = 0;
  v79 = 0;
  if ( DWORD1(v85) )
  {
    if ( (BYTE8(v85) & 4) != 0 )
    {
      if ( DWORD1(v85) == 1 )
      {
        if ( (a2->Iopb->Parameters.Create.Options & 1) != 0 )
          MicrosoftTelemetryAssertTriggeredMsgKM("!FlagOn(Cbd.Iopb->Parameters.Create.Options, FILE_DIRECTORY_FILE)");
        v16 = v86[1];
        v17 = 0;
        v18 = v86[0];
        if ( v86[1] )
          _InterlockedIncrement((volatile signed __int32 *)v86[1] + 2);
        *((_QWORD *)a5 + 21) = v18;
        v19 = (utl::_RefCountBase *)*((_QWORD *)a5 + 22);
        *((_QWORD *)a5 + 22) = v16;
        if ( !v19 )
          goto LABEL_160;
        goto LABEL_159;
      }
      a2->IoStatus.Status = -1073741766;
      a2->IoStatus.Information = 0;
      *a4 = FLT_PREOP_COMPLETE;
      v17 = 0;
      goto LABEL_160;
    }
    if ( (_DWORD)v88 == 1 )
    {
      **((_DWORD **)a5 + 20) |= 8u;
      goto LABEL_161;
    }
    if ( *((_WORD *)v86[0] + 80) == 4 )
    {
      if ( !*((_QWORD *)v86[0] + 26) )
        MicrosoftTelemetryAssertTriggeredMsgKM("results.CacheEntry->GetOriginalScratchPath()");
      if ( DWORD1(v85) == 1 )
      {
        if ( (a2->Iopb->Parameters.Create.Options & 0x40) == 0 )
          MicrosoftTelemetryAssertTriggeredMsgKM("Failing supersede on exact match for renamed tombstone");
        v15 = -1073741638;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000BALL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x387000205BELL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
          "ORIGIN: Attempt to supersede a directory by opening it as a non-directory",
          (const char *)a6);
        goto LABEL_161;
      }
    }
    else if ( DWORD1(v85) == 1 )
    {
      v8 = (volatile signed __int32 *)*((_QWORD *)v86[0] + 5);
      v20 = (_QWORD **)*((_QWORD *)v86[0] + 4);
      P = v20;
      if ( v8 )
        _InterlockedIncrement(v8 + 2);
      memset(v98, 0, 0x48u);
      HostSilo = (unsigned int *)PsGetHostSilo(v22, v21);
      v24 = *v20[1];
      *(_OWORD *)Resource = *(_OWORD *)*((_QWORD *)v86[0] + 6);
      v15 = UnionFs::Utils::StatItemAsCaller(
              (const char *)Resource,
              v24,
              HostSilo,
              4,
              (__int64)v98,
              (UnionFs::Utils *)a2,
              (int)a6);
      if ( v15 < 0 )
      {
        v25 = "PUSH: Stat layer item";
        v26 = 0x221000205DALL;
LABEL_30:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v15,
          (int)a6,
          (struct UnionFs::StackEventTracer *)v26,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
          v25,
          (const char *)v75);
        goto LABEL_31;
      }
      if ( v15 == 260 )
        goto LABEL_34;
      v27 = v86[0];
      v79 = v98[17];
      FltReferenceContext(*((PFLT_CONTEXT *)v86[0] + 9));
      Context[0] = *((PFLT_CONTEXT *)v27 + 9);
      v28 = (struct UnionFs::UfsStreamHandleCtx *)*((_QWORD *)Context[0] + 4);
      FsFltWil::AcquireResourceExclusive(Resource, *((_QWORD *)v28 + 15) + 56LL);
      Iopb = a2->Iopb;
      v92 = 0;
      v30 = v78;
      v31 = *(unsigned int *)(*(_QWORD *)(Iopb->Parameters.WMI.ProviderId + 8) + 24LL);
      *(_WORD *)((char *)&v90.Buffer + 5) = 0;
      LODWORD(v31) = v31 | 0x10000;
      HIBYTE(v90.Buffer) = 0;
      v93 = 0;
      v94 = 0;
      *(_DWORD *)(&v90.MaximumLength + 1) = 1;
      BYTE4(v90.Buffer) = 1;
      *(_DWORD *)&v90.Length = v31;
      LODWORD(v90.Buffer) = v31;
      v91 = 2;
      v75 = v28;
      v15 = UnionFs::UnionFsFilter::CheckOplockAndShareAccess(v31, a2, v78, Context, &v90);
      if ( v15 >= 0 )
      {
        if ( v15 != 259 )
        {
          if ( Resource[0] )
          {
            ExReleaseResourceLite(Resource[0]);
            KeLeaveCriticalRegion();
          }
          if ( Context[0] )
            FltReleaseContext(Context[0]);
          goto LABEL_54;
        }
        *a4 = FLT_PREOP_PENDING;
        v15 = 0;
      }
      else
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v15,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x6E40002060ALL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
          "PUSH: Oplock and share access check",
          (const char *)v75);
      }
      if ( Resource[0] )
      {
        ExReleaseResourceLite(Resource[0]);
        KeLeaveCriticalRegion();
      }
      if ( Context[0] )
        FltReleaseContext(Context[0]);
      goto LABEL_31;
    }
    v32 = v87;
    v87 = 0;
    if ( v32 )
    {
      ExReleaseResourceLite(v32);
      KeLeaveCriticalRegion();
    }
    v33 = v86[1];
    v86[1] = 0;
    v86[0] = 0;
    if ( v33 )
      utl::_RefCountBase::_DecStrong(v33);
  }
  v30 = v78;
LABEL_54:
  Context[0] = 0;
  if ( (_DWORD)v88 != 2 )
    goto LABEL_63;
  v34 = (UnionFs::Rtl *)(*(_QWORD *)a5 + 8LL);
  *(_OWORD *)Resource = **((_OWORD **)&v89 + 1);
  v90 = *(struct _UNICODE_STRING *)v89;
  v17 = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(
          v34,
          &v90,
          (PCUNICODE_STRING)Resource,
          Context,
          (int)a6);
  if ( v17 < 0 )
  {
    v37 = "PUSH: Replacing substring";
    v38 = 0x37F00020639LL;
LABEL_57:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v17,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v38,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
      v37,
      (const char *)v75);
    v40 = (char *)Context[0];
    if ( !Context[0] )
      goto LABEL_157;
    if ( !*((_BYTE *)Context[0] + 16) )
      *(_OWORD *)Context[0] = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v40, v39);
    goto LABEL_61;
  }
  v41 = Context[0];
  v17 = 0;
  if ( !Context[0] )
  {
LABEL_63:
    v17 = UnionFs::UfsPathName::AllocAndInit(*(_QWORD *)a5, Context, a6);
    if ( v17 < 0 )
    {
      v37 = "PUSH: Allocating scratch path for layer lookup";
      v38 = 0x36900020644LL;
      goto LABEL_57;
    }
    v41 = Context[0];
    v17 = 0;
  }
  v42 = *((_QWORD *)a5 + 20);
  v43 = *(_QWORD *)(v42 + 64);
  *(_QWORD *)(v42 + 64) = v41;
  if ( v43 )
  {
    if ( !*(_BYTE *)(v43 + 16) )
      *(_OWORD *)v43 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v43, v35);
    ExFreePoolWithTag((PVOID)v43, 0);
  }
  v44 = v86[0];
  if ( v86[0] )
  {
    v45 = v79;
    v46 = 0;
    v47 = 0;
    goto LABEL_129;
  }
  v96[0] = off_14007E740;
  v96[13] = v96;
  UnionFs::StackEventTracer::SetIgnoreStatusCallback(a6, v95);
  memset(v97, 0, 0x48u);
  v75 = a6;
  v15 = UnionFs::Utils::StatItemAsCaller(*(_QWORD *)a5 + 8LL, v30->Instance, v48, v97, a2);
  v49 = *((_WORD *)a6 + 245);
  if ( v49 )
  {
    v50 = v49 - 1;
    *((_WORD *)a6 + 245) = v50;
    v51 = 120 * (v50 + 1LL);
    v52 = *(_QWORD *)((char *)a6 + v51);
    *(_QWORD *)((char *)a6 + v51) = 0;
    if ( v52 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v52 + 24LL))(v52, v51, 1);
  }
  if ( v15 == 260 )
    goto LABEL_34;
  if ( v15 >= 0 )
  {
    if ( !v15 )
    {
      v46 = 1;
      v47 = 0;
LABEL_128:
      v45 = DWORD1(v97[4]);
      v44 = v86[0];
LABEL_129:
      if ( ((*(_DWORD *)(*(_QWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 8) + 20LL) | v45) & 0x10000) != 0 )
      {
        if ( !v46 )
        {
          LOBYTE(Resource[1]) = 1;
          Resource[0] = (PERESOURCE)v84;
          *(_OWORD *)v84 = 0;
          if ( !v47 )
          {
            if ( v44 )
            {
              v66 = v89;
              Context[0] = *((PFLT_CONTEXT *)a5 + 1);
              v67 = (volatile signed __int32 *)*((_QWORD *)a5 + 2);
              Context[1] = (PFLT_CONTEXT)v67;
              if ( v67 )
                _InterlockedIncrement(v67 + 2);
              v15 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v44, Context, v66, 9, a6);
              if ( v15 < 0 )
              {
                UnionFs::ProcessTraceStatusPushLocation(
                  (UnionFs *)(unsigned int)v15,
                  (int)a6,
                  (struct UnionFs::StackEventTracer *)0x46D000206EBLL,
                  (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
                  "PUSH: ConvertToSoftTombstone for COW",
                  (const char *)v75);
                goto LABEL_137;
              }
              v68 = v86[1];
              v69 = v86[0];
              if ( v86[1] )
                _InterlockedIncrement((volatile signed __int32 *)v86[1] + 2);
              v84[0] = v69;
              v70 = v84[1];
              v84[1] = v68;
              if ( v70 )
                utl::_RefCountBase::_DecStrong(v70);
              v71 = v87;
              v87 = 0;
              if ( v71 )
              {
                ExReleaseResourceLite(v71);
                KeLeaveCriticalRegion();
              }
            }
            v72 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
                    *((UnionFs::UfsUnionCtx **)a5 + 1),
                    a2,
                    v78,
                    *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
                    *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
                    *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
                    (const struct UnionFs::UfsLayerCtx *)P,
                    a6,
                    v83);
            v15 = v72;
            if ( v72 < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)v72,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0xE3000206FELL,
                (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
                "PUSH: Preparing for scratch create",
                (const char *)v77);
LABEL_137:
              wil::details::lambda_call__lambda_6ee8654c966d7d18060a2995f0b9aa38___::_lambda_call__lambda_6ee8654c966d7d18060a2995f0b9aa38___(Resource);
              if ( v84[1] )
                utl::_RefCountBase::_DecStrong(v84[1]);
              goto LABEL_31;
            }
            v44 = v86[0];
          }
          *((_QWORD *)a5 + 24) = 0;
          *((_BYTE *)a5 + 186) = 1;
          if ( v44 )
          {
            UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(v44, 0x43700020708LL);
            UnionFs::UfsPathCachePayload::RevertSoftTombstone(v44);
            LOBYTE(Resource[1]) = 0;
          }
          wil::details::lambda_call__lambda_6ee8654c966d7d18060a2995f0b9aa38___::_lambda_call__lambda_6ee8654c966d7d18060a2995f0b9aa38___(Resource);
          if ( v84[1] )
            utl::_RefCountBase::_DecStrong(v84[1]);
        }
      }
      else
      {
        if ( (unsigned int)dword_14009E178 > 4
          && (qword_14009E188 & 0x200) != 0
          && (qword_14009E190 & 0x200) == qword_14009E190 )
        {
          v79 = v45;
          v83 = (struct UnionFs::UfsSiloCtx *)"onecore\\base\\fs\\unionfs\\sys\\create.cpp";
          LODWORD(v78) = 1812;
          Resource[0] = (PERESOURCE)"Caller does not have DELETE access";
          P = (PVOID)"UnionFs::UnionFsFilter::PreCreateFileSupersede";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
            (unsigned int)&word_140095F1E,
            v45,
            v36,
            (__int64)Resource,
            (__int64)&P,
            (__int64)&v83,
            (__int64)&v78,
            (__int64)&v79);
        }
        v73 = v84[0];
        a2->IoStatus.Status = -1073741790;
        a2->IoStatus.Information = 0;
        *(_DWORD *)v73 = 4;
      }
LABEL_157:
      if ( v8 )
      {
        v19 = (utl::_RefCountBase *)v8;
LABEL_159:
        utl::_RefCountBase::_DecStrong(v19);
      }
LABEL_160:
      v15 = v17;
      goto LABEL_161;
    }
    MicrosoftTelemetryAssertTriggeredMsgKM("foundInScratch || Utils::IsObjectNotFoundStatus(status)");
    goto LABEL_85;
  }
  if ( v15 == -1073741766 )
  {
LABEL_85:
    v47 = 0;
    goto LABEL_86;
  }
  if ( v15 != -1073741772 )
  {
    v25 = "PUSH: Querying stat information";
    v26 = 0xD500020667LL;
    goto LABEL_30;
  }
  v47 = 1;
LABEL_86:
  utl::make_unique<UnionFs::FindAndStatResults,,0>(&P);
  v40 = (char *)P;
  if ( !P )
  {
    v15 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x3FA00020679LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
      "ORIGIN: Allocating findAndStatResults",
      (const char *)a6);
LABEL_31:
    if ( v8 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v8);
    goto LABEL_161;
  }
  v53 = *((_QWORD *)a5 + 1);
  v75 = (struct UnionFs::UfsStreamHandleCtx *)P;
  v90 = *(struct _UNICODE_STRING *)*(_QWORD *)(*((_QWORD *)a5 + 20) + 64LL);
  v54 = UnionFs::UfsUnionCtx::FindAndStatItemInLayersAsCaller(v53, a2, &v90);
  v17 = v54;
  if ( v54 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v54,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0xE100020683LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
      "PUSH: Probing for item in layers",
      (const char *)v75);
    if ( v40 )
    {
      v55 = (utl::_RefCountBase *)*((_QWORD *)v40 + 11);
      if ( v55 )
        utl::_RefCountBase::_DecStrong(v55);
LABEL_61:
      ExFreePoolWithTag(v40, 0);
      goto LABEL_157;
    }
    goto LABEL_157;
  }
  if ( v54 == 260 )
  {
    if ( v40 )
    {
      v56 = (utl::_RefCountBase *)*((_QWORD *)v40 + 11);
      if ( v56 )
        utl::_RefCountBase::_DecStrong(v56);
      ExFreePoolWithTag(v40, 0);
    }
LABEL_34:
    if ( v8 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v8);
    v15 = 260;
    goto LABEL_161;
  }
  v97[0] = *(_OWORD *)(v40 + 8);
  v97[1] = *(_OWORD *)(v40 + 24);
  v97[2] = *(_OWORD *)(v40 + 40);
  v97[3] = *(_OWORD *)(v40 + 56);
  *(_QWORD *)&v97[4] = *((_QWORD *)v40 + 9);
  v57 = (volatile signed __int32 *)*((_QWORD *)v40 + 11);
  v58 = (PVOID)*((_QWORD *)v40 + 10);
  P = v58;
  if ( v57 )
    _InterlockedIncrement(v57 + 2);
  if ( v8 )
  {
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v8);
    v58 = P;
  }
  v59 = *(_WORD *)v40;
  if ( *(_WORD *)v40 == 2 )
  {
    if ( !v47 )
    {
      v60 = v84[0];
      a2->IoStatus.Status = -1073741766;
      a2->IoStatus.Information = 0;
      *(_DWORD *)v60 = 4;
    }
    goto LABEL_104;
  }
  if ( v59 != 3 )
  {
    v8 = v57;
    if ( v59 != 1 )
      MicrosoftTelemetryAssertTriggeredMsgKM("findAndStatResults->FindResult == LAYER_FIND_RESULT::Found");
    v17 = 0;
    if ( v40 )
    {
      v65 = (utl::_RefCountBase *)*((_QWORD *)v40 + 11);
      if ( v65 )
        utl::_RefCountBase::_DecStrong(v65);
      ExFreePoolWithTag(v40, 0);
    }
    v46 = 0;
    goto LABEL_128;
  }
  if ( v47
    || (v62 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
                *((UnionFs::UfsUnionCtx **)a5 + 1),
                a2,
                v78,
                *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
                *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
                *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
                (const struct UnionFs::UfsLayerCtx *)v58,
                a6,
                v83),
        v63 = v62,
        v62 >= 0) )
  {
LABEL_104:
    if ( v40 )
    {
      v61 = (utl::_RefCountBase *)*((_QWORD *)v40 + 11);
      if ( v61 )
        utl::_RefCountBase::_DecStrong(v61);
      ExFreePoolWithTag(v40, 0);
    }
    if ( v57 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v57);
    v15 = 0;
    goto LABEL_161;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v62,
    (int)a6,
    (struct UnionFs::StackEventTracer *)0xE2000206AFLL,
    (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
    "PUSH: Preparing for scratch create",
    (const char *)v76);
  if ( v40 )
  {
    v64 = (utl::_RefCountBase *)*((_QWORD *)v40 + 11);
    if ( v64 )
      utl::_RefCountBase::_DecStrong(v64);
    ExFreePoolWithTag(v40, 0);
  }
  if ( v57 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v57);
  v15 = v63;
LABEL_161:
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v85);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140019438  mov     [rsp-8+arg_0], rbx
0x14001943d  push    rbp
0x14001943e  push    rsi
0x14001943f  push    rdi
0x140019440  push    r12
0x140019442  push    r13
0x140019444  push    r14
0x140019446  push    r15
0x140019448  lea     rbp, [rsp-130h]
0x140019450  sub     rsp, 230h
0x140019457  mov     rax, cs:__security_cookie
0x14001945e  xor     rax, rsp
0x140019461  mov     [rbp+160h+var_40], rax
0x140019468  mov     rax, [rbp+160h+arg_30]
0x14001946f  mov     r15, r9
0x140019472  mov     r14, [rbp+160h+arg_20]
0x140019479  xor     edi, edi
0x14001947b  mov     rsi, [rbp+160h+arg_28]
0x140019482  xorps   xmm1, xmm1
0x140019485  mov     [r9], edi
0x140019488  xorps   xmm0, xmm0
0x14001948b  mov     [rbp+160h+var_1C8], r9
0x14001948f  mov     r10, r8
0x140019492  mov     [rbp+160h+var_1D0], rax
0x140019496  mov     r13, rdx
0x140019499  mov     rax, [r8+20h]
0x14001949d  mov     [rsp+260h+var_208], r8
0x1400194a2  mov     r9d, [rax+50h]
0x1400194a6  shr     r9d, 11h
0x1400194aa  movd    eax, xmm1
0x1400194ae  not     r9d
0x1400194b1  movdqa  [rbp+160h+var_1B0], xmm1
0x1400194b6  and     r9d, 1
0x1400194ba  or      r9d, 8
0x1400194be  movdqa  xmmword ptr [rbp+160h+var_1A0], xmm0
0x1400194c3  or      eax, 3
0x1400194c6  mov     [rbp+160h+var_190], rdi
0x1400194ca  mov     dword ptr [rbp+160h+var_1B0], eax
0x1400194cd  mov     rax, [r14+8]
0x1400194d1  mov     [rbp+160h+var_188], rdi
0x1400194d5  movdqa  [rbp+160h+var_180], xmm0
0x1400194da  cmp     dword ptr [rax+1Ch], 2
0x1400194de  jnz     short loc_1400194EA
0x1400194e0  mov     rax, [rax+20h]
0x1400194e4  mov     rcx, [rax+10h]
0x1400194e8  jmp     short loc_1400194F5
0x1400194ea  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400194f1  mov     rcx, [rax+50h]
0x1400194f5  mov     r8, [r14]
0x1400194f8  lea     rax, [rbp+160h+var_1B0]
0x1400194fc  mov     rdx, [r10+18h]
0x140019500  mov     [rsp+260h+var_230], r13
0x140019505  mov     [rsp+260h+var_238], rsi; char *
0x14001950a  mov     [rsp+260h+var_240], rax
0x14001950f  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140019514  mov     ebx, eax
0x140019516  test    eax, eax
0x140019518  jns     short loc_140019546
0x14001951a  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x140019521  mov     r8, 22000020581h; struct UnionFs::StackEventTracer *
0x14001952b  lea     r9, aUnionfsUnionfs_58; "UnionFs::UnionFsFilter::PreCreateFileSu"...
0x140019532  mov     [rsp+260h+var_240], rax; char *
0x140019537  mov     rdx, rsi; int
0x14001953a  mov     ecx, ebx; this
0x14001953c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140019541  jmp     loc_14001A0CD
0x140019546  mov     eax, dword ptr [rbp+160h+var_1B0+4]
0x140019549  xor     ebx, ebx
0x14001954b  mov     [rsp+260h+P], rbx
0x140019550  mov     [rsp+260h+var_200], ebx
0x140019554  lea     r8d, [rbx+4]
0x140019558  test    eax, eax
0x14001955a  jz      loc_14001990A
0x140019560  test    byte ptr [rbp+160h+var_1B0+8], r8b
0x140019564  jz      short loc_1400195D2
0x140019566  lea     edx, [rbx+1]
0x140019569  cmp     eax, edx
0x14001956b  jnz     short loc_1400195BB
0x14001956d  mov     rax, [r13+10h]
0x140019571  mov     ecx, [rax+20h]
0x140019574  test    dl, cl
0x140019576  jz      short loc_140019584
0x140019578  lea     rcx, aFlagonCbdIopbP; "!FlagOn(Cbd.Iopb->Parameters.Create.Opt"...
0x14001957f  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140019584  mov     rax, [rbp+160h+var_1A0+8]
0x140019588  xor     r15d, r15d
0x14001958b  mov     rcx, [rbp+160h+var_1A0]
0x14001958f  test    rax, rax
0x140019592  jz      short loc_140019598
0x140019594  lock inc dword ptr [rax+8]
0x140019598  mov     [r14+0A8h], rcx
0x14001959f  mov     rcx, [r14+0B0h]
0x1400195a6  mov     [r14+0B0h], rax
0x1400195ad  test    rcx, rcx
0x1400195b0  jz      loc_14001A0CA
0x1400195b6  jmp     loc_14001A0C5
0x1400195bb  mov     dword ptr [r13+18h], 0C000003Ah
0x1400195c3  mov     [r13+20h], rbx
0x1400195c7  mov     [r15], r8d
0x1400195ca  xor     r15d, r15d
0x1400195cd  jmp     loc_14001A0CA
0x1400195d2  mov     r12d, 1
0x1400195d8  cmp     dword ptr [rbp+160h+var_188], r12d
0x1400195dc  jnz     short loc_1400195ED
0x1400195de  mov     rax, [r14+0A0h]
0x1400195e5  or      dword ptr [rax], 8
0x1400195e8  jmp     loc_14001A0CD
0x1400195ed  mov     rax, [rbp+160h+var_1A0]
0x1400195f1  movzx   ecx, word ptr [rax+0A0h]
0x1400195f8  nop
0x1400195f9  cmp     cx, r8w
0x1400195fd  jnz     short loc_14001966B
0x1400195ff  mov     rax, [rbp+160h+var_1A0]
0x140019603  cmp     [rax+0D0h], rbx
0x14001960a  jnz     short loc_140019618
0x14001960c  lea     rcx, aResultsCacheen; "results.CacheEntry->GetOriginalScratchP"...
0x140019613  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140019618  cmp     dword ptr [rbp+160h+var_1B0+4], r12d
0x14001961c  jnz     loc_1400198CF
0x140019622  mov     rax, [r13+10h]
0x140019626  mov     ecx, [rax+20h]
0x140019629  test    cl, 40h
0x14001962c  jnz     short loc_14001963A
0x14001962e  lea     rcx, aFailingSuperse; "Failing supersede on exact match for re"...
0x140019635  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001963a  lea     rax, aOriginAttemptT; "ORIGIN: Attempt to supersede a director"...
0x140019641  mov     ebx, 0C00000BAh
0x140019646  mov     ecx, ebx; this
0x140019648  mov     [rsp+260h+var_240], rax; char *
0x14001964d  lea     r9, aUnionfsUnionfs_58; "UnionFs::UnionFsFilter::PreCreateFileSu"...
0x140019654  mov     r8, 387000205BEh; struct UnionFs::StackEventTracer *
0x14001965e  mov     rdx, rsi; int
0x140019661  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140019666  jmp     loc_14001A0CD
0x14001966b  cmp     dword ptr [rbp+160h+var_1B0+4], r12d
0x14001966f  jnz     loc_1400198CF
0x140019675  mov     rax, [rbp+160h+var_1A0]
0x140019679  mov     rdi, [rax+28h]
0x14001967d  mov     r12, [rax+20h]
0x140019681  mov     [rsp+260h+P], r12
0x140019686  test    rdi, rdi
0x140019689  jz      short loc_14001968F
0x14001968b  lock inc dword ptr [rdi+8]
0x14001968f  xor     edx, edx; Val
0x140019691  lea     rcx, [rbp+160h+var_90]; void *
0x140019698  lea     r8d, [rdx+48h]; Size
0x14001969c  call    memset
0x1400196a1  call    cs:__imp_PsGetHostSilo
0x1400196a8  nop     dword ptr [rax+rax+00h]
0x1400196ad  mov     rcx, [r12+8]
0x1400196b2  mov     r9d, 4
0x1400196b8  mov     [rsp+260h+var_230], rsi
0x1400196bd  mov     r8, rax
0x1400196c0  mov     [rsp+260h+var_238], r13; char *
0x1400196c5  mov     r10, [rcx]
0x1400196c8  mov     rcx, [rbp+160h+var_1A0]
0x1400196cc  mov     rdx, [rcx+30h]
0x1400196d0  lea     rcx, [rbp+160h+var_90]
0x1400196d7  mov     [rsp+260h+var_240], rcx
0x1400196dc  lea     rcx, [rsp+260h+Resource]
0x1400196e1  movups  xmm0, xmmword ptr [rdx]
0x1400196e4  mov     rdx, r10
0x1400196e7  movdqu  xmmword ptr [rsp+260h+Resource], xmm0
0x1400196ed  call    ?StatItemAsCaller@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::StatItemAsCaller(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x1400196f2  xor     r12d, r12d
0x1400196f5  mov     ebx, eax
0x1400196f7  test    eax, eax
0x1400196f9  jns     short loc_140019738
0x1400196fb  lea     rax, aPushStatLayerI; "PUSH: Stat layer item"
0x140019702  mov     r8, 221000205DAh; struct UnionFs::StackEventTracer *
0x14001970c  lea     r9, aUnionfsUnionfs_58; "UnionFs::UnionFsFilter::PreCreateFileSu"...
0x140019713  mov     [rsp+260h+var_240], rax; char *
0x140019718  mov     rdx, rsi; int
0x14001971b  mov     ecx, ebx; this
0x14001971d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140019722  test    rdi, rdi
0x140019725  jz      loc_14001A0CD
0x14001972b  mov     rcx, rdi; this
0x14001972e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140019733  jmp     loc_14001A0CD
0x140019738  cmp     ebx, 104h
0x14001973e  jnz     short loc_140019757
0x140019740  test    rdi, rdi
0x140019743  jz      short loc_14001974D
0x140019745  mov     rcx, rdi; this
0x140019748  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001974d  mov     ebx, 104h
0x140019752  jmp     loc_14001A0CD
0x140019757  mov     rbx, [rbp+160h+var_1A0]
0x14001975b  mov     eax, [rbp+160h+var_4C]
0x140019761  mov     [rsp+260h+var_200], eax
0x140019765  mov     rcx, [rbx+48h]; Context
0x140019769  call    cs:__imp_FltReferenceContext
0x140019770  nop     dword ptr [rax+rax+00h]
0x140019775  mov     rax, [rbx+48h]
0x140019779  lea     rcx, [rsp+260h+Resource]
0x14001977e  mov     [rbp+160h+Context], rax
0x140019782  mov     rbx, [rax+20h]
0x140019786  mov     rdx, [rbx+78h]
0x14001978a  add     rdx, 38h ; '8'
0x14001978e  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140019793  mov     rax, [r13+10h]
0x140019797  lea     r9, [rbp+160h+Context]
0x14001979b  mov     [rsp+260h+var_220], rsi
0x1400197a0  mov     rdx, r13
0x1400197a3  mov     [rsp+260h+var_228], r14
0x1400197a8  mov     [rbp+160h+var_15C], r12b
0x1400197ac  mov     rcx, [rax+18h]
0x1400197b0  mov     [rsp+260h+var_210], r12b
0x1400197b5  mov     r12, [rsp+260h+var_208]
0x1400197ba  mov     rax, [rcx+8]
0x1400197be  mov     ecx, [rax+18h]
0x1400197c1  xor     eax, eax
0x1400197c3  mov     word ptr [rbp+160h+var_170.Buffer+5], ax
0x1400197c7  bts     ecx, 10h
0x1400197cb  mov     byte ptr [rbp+160h+var_170.Buffer+7], al
0x1400197ce  mov     [rbp+160h+var_15B], ax
0x1400197d2  mov     [rbp+160h+var_159], al
0x1400197d5  mov     eax, 1
0x1400197da  mov     dword ptr [rbp+160h+var_170+4], eax
0x1400197dd  mov     byte ptr [rbp+160h+var_170.Buffer+4], al
0x1400197e0  mov     dword ptr [rbp+160h+var_170.Length], ecx
0x1400197e3  lea     r8d, [rax+1]
0x1400197e7  mov     dword ptr [rbp+160h+var_170.Buffer], ecx
0x1400197ea  lea     rax, [rsp+260h+var_210]
0x1400197ef  mov     [rbp+160h+var_160], r8d
0x1400197f3  mov     [rsp+260h+var_230], rax
0x1400197f8  mov     r8, r12
0x1400197fb  lea     rax, [rbp+160h+var_170]
0x1400197ff  mov     [rsp+260h+var_238], rbx; char *
0x140019804  mov     [rsp+260h+var_240], rax
0x140019809  call    ?CheckOplockAndShareAccess@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@$$QEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBUCheckOplockAndShareAccessParams@12@AEAVUfsFsContext@2@PEA_NAEAUCreateContext@2@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::CheckOplockAndShareAccess(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &&,UnionFs::UnionFsFilter::CheckOplockAndShareAccessParams const &,UnionFs::UfsFsContext &,bool *,UnionFs::CreateContext &,UnionFs::StackEventTracer &)
0x14001980e  mov     ebx, eax
0x140019810  test    eax, eax
0x140019812  jns     short loc_14001987B
0x140019814  lea     rax, aPushOplockAndS; "PUSH: Oplock and share access check"
0x14001981b  mov     r8, 6E40002060Ah; struct UnionFs::StackEventTracer *
0x140019825  lea     r9, aUnionfsUnionfs_58; "UnionFs::UnionFsFilter::PreCreateFileSu"...
0x14001982c  mov     [rsp+260h+var_240], rax; char *
0x140019831  mov     rdx, rsi; int
0x140019834  mov     ecx, ebx; this
0x140019836  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001983b  mov     rcx, [rsp+260h+Resource]; Resource
0x140019840  test    rcx, rcx
0x140019843  jz      short loc_14001985D
0x140019845  call    cs:__imp_ExReleaseResourceLite
0x14001984c  nop     dword ptr [rax+rax+00h]
0x140019851  call    cs:__imp_KeLeaveCriticalRegion
0x140019858  nop     dword ptr [rax+rax+00h]
0x14001985d  mov     rcx, [rbp+160h+Context]; Context
0x140019861  test    rcx, rcx
0x140019864  jz      loc_140019722
0x14001986a  call    cs:__imp_FltReleaseContext
0x140019871  nop     dword ptr [rax+rax+00h]
0x140019876  jmp     loc_140019722
0x14001987b  cmp     ebx, 103h
0x140019881  jnz     short loc_14001988E
0x140019883  mov     dword ptr [r15], 2
0x14001988a  xor     ebx, ebx
0x14001988c  jmp     short loc_14001983B
0x14001988e  xor     ebx, ebx
0x140019890  cmp     [rsp+260h+var_210], bl
0x140019894  jnz     short loc_14001983B
0x140019896  mov     rcx, [rsp+260h+Resource]; Resource
0x14001989b  test    rcx, rcx
0x14001989e  jz      short loc_1400198B8
0x1400198a0  call    cs:__imp_ExReleaseResourceLite
0x1400198a7  nop     dword ptr [rax+rax+00h]
0x1400198ac  call    cs:__imp_KeLeaveCriticalRegion
0x1400198b3  nop     dword ptr [rax+rax+00h]
0x1400198b8  mov     rcx, [rbp+160h+Context]; Context
0x1400198bc  test    rcx, rcx
0x1400198bf  jz      short loc_14001990F
0x1400198c1  call    cs:__imp_FltReleaseContext
0x1400198c8  nop     dword ptr [rax+rax+00h]
0x1400198cd  jmp     short loc_14001990F
0x1400198cf  mov     rcx, [rbp+160h+var_190]; Resource
0x1400198d3  mov     [rbp+160h+var_190], rbx
0x1400198d7  test    rcx, rcx
0x1400198da  jz      short loc_1400198F4
0x1400198dc  call    cs:__imp_ExReleaseResourceLite
0x1400198e3  nop     dword ptr [rax+rax+00h]
0x1400198e8  call    cs:__imp_KeLeaveCriticalRegion
0x1400198ef  nop     dword ptr [rax+rax+00h]
0x1400198f4  mov     rcx, [rbp+160h+var_1A0+8]; this
0x1400198f8  mov     [rbp+160h+var_1A0+8], rbx
0x1400198fc  mov     [rbp+160h+var_1A0], rbx
0x140019900  test    rcx, rcx
0x140019903  jz      short loc_14001990A
0x140019905  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001990a  mov     r12, [rsp+260h+var_208]
0x14001990f  cmp     dword ptr [rbp+160h+var_188], 2
0x140019913  mov     [rbp+160h+Context], rbx
0x140019917  jnz     loc_1400199D0
0x14001991d  mov     rax, qword ptr [rbp+160h+var_180+8]
0x140019921  lea     r8, [rsp+260h+Resource]; Source
0x140019926  mov     rcx, [r14]
0x140019929  lea     rdx, [rbp+160h+var_170]; struct _UNICODE_STRING *
0x14001992d  add     rcx, 8; this
0x140019931  mov     [rsp+260h+var_238], rsi; char *
  ... truncated ...
```
