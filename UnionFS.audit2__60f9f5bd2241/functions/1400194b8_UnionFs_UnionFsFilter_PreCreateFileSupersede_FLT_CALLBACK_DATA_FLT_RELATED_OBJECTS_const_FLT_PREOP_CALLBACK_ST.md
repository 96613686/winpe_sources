# UnionFs::UnionFsFilter::PreCreateFileSupersede(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x1400194b8`
- end: `0x14001a183`
- name: `?PreCreateFileSupersede@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `3275`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x140011e20`

## callees

- `0x14000110c`
- `0x14000efa0`
- `0x14000f81c`
- `0x140010ba8`
- `0x140010f74`
- `0x1400111b8`
- `0x1400114e4`
- `0x1400194b8`
- `0x14003cea8`
- `0x140041b30`
- `0x140042674`
- `0x14004327c`
- `0x140043afc`
- `0x140044074`
- `0x140056c44`
- `0x140056c7c`
- `0x140061058`
- `0x14006127c`
- `0x1400782bc`
- `0x14007862c`
- `0x140079d8c`
- `0x140079f68`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140019a33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ab0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ccc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019d83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e97`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019a33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ab0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ccc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019d83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019e97`
- `ntoskrnl!PsGetHostSilo` at `0x140019721`
- `ntoskrnl!PsGetHostSilo` at `0x140019721`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400198c5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019920`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001995c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019fb4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400198c5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019920`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001995c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019fb4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400198d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001992c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019968`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019fc0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400198d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001992c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019968`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019fc0`
- `FLTMGR!FltReferenceContext` at `0x1400197e9`
- `FLTMGR!FltReferenceContext` at `0x1400197e9`
- `FLTMGR!FltReleaseContext` at `0x1400198ea`
- `FLTMGR!FltReleaseContext` at `0x140019941`
- `FLTMGR!FltReleaseContext` at `0x1400198ea`
- `FLTMGR!FltReleaseContext` at `0x140019941`

## string_xrefs

- `0x14001a0ba`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x14001959a`: `PUSH: Cache lookup`
- `0x14001968c`: `results.CacheEntry->GetOriginalScratchPath()`
- `0x140019a66`: `PUSH: Allocating scratch path for layer lookup`
- `0x1400195ab`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x1400196cd`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x14001978c`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x1400198a5`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x1400199f6`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019c0b`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019c70`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019e1a`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x140019f53`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x14001a0ca`: `UnionFs::UnionFsFilter::PreCreateFileSupersede`
- `0x1400195f8`: `!FlagOn(Cbd.Iopb->Parameters.Create.Options, FILE_DIRECTORY_FILE)`
- `0x1400196ae`: `Failing supersede on exact match for renamed tombstone`
- `0x1400196ba`: `ORIGIN: Attempt to supersede a directory by opening it as a non-directory`
- `0x140019894`: `PUSH: Oplock and share access check`
- `0x140019e04`: `PUSH: Preparing for scratch create`
- `0x14001a013`: `PUSH: Preparing for scratch create`
- `0x14001a0d1`: `Caller does not have DELETE access`

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
      (struct UnionFs::StackEventTracer *)0x22000020571LL,
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
    if ( *((_WORD *)v86[0] + 84) == 4 )
    {
      if ( !*((_QWORD *)v86[0] + 27) )
        MicrosoftTelemetryAssertTriggeredMsgKM("results.CacheEntry->GetOriginalScratchPath()");
      if ( DWORD1(v85) == 1 )
      {
        if ( (a2->Iopb->Parameters.Create.Options & 0x40) == 0 )
          MicrosoftTelemetryAssertTriggeredMsgKM("Failing supersede on exact match for renamed tombstone");
        v15 = -1073741638;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000BALL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x387000205AELL,
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
        v26 = 0x221000205CALL;
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
          (struct UnionFs::StackEventTracer *)0x6E4000205FALL,
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
    v38 = 0x37F00020629LL;
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
      v38 = 0x36900020634LL;
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
  v96[0] = off_14007E748;
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
                  (struct UnionFs::StackEventTracer *)0x46D000206DBLL,
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
                (struct UnionFs::StackEventTracer *)0xE3000206EELL,
                (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
                "PUSH: Preparing for scratch create",
                (const char *)v77);
LABEL_137:
              wil::details::lambda_call__lambda_f39ac3ecaf503c5c14215d99ffc82e5e___::_lambda_call__lambda_f39ac3ecaf503c5c14215d99ffc82e5e___(Resource);
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
            UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(v44, 0x437000206F8LL);
            UnionFs::UfsPathCachePayload::RevertSoftTombstone(v44);
            LOBYTE(Resource[1]) = 0;
          }
          wil::details::lambda_call__lambda_f39ac3ecaf503c5c14215d99ffc82e5e___::_lambda_call__lambda_f39ac3ecaf503c5c14215d99ffc82e5e___(Resource);
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
          LODWORD(v78) = 1796;
          Resource[0] = (PERESOURCE)"Caller does not have DELETE access";
          P = (PVOID)"UnionFs::UnionFsFilter::PreCreateFileSupersede";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)"UnionFs::UnionFsFilter::PreCreateFileSupersede",
            (unsigned int)&word_140095F9E,
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
    v26 = 0xD500020657LL;
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
      (struct UnionFs::StackEventTracer *)0x3FA00020669LL,
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
      (struct UnionFs::StackEventTracer *)0xE100020673LL,
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
    (struct UnionFs::StackEventTracer *)0xE20002069FLL,
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
0x1400194b8  mov     [rsp-8+arg_0], rbx
0x1400194bd  push    rbp
0x1400194be  push    rsi
0x1400194bf  push    rdi
0x1400194c0  push    r12
0x1400194c2  push    r13
0x1400194c4  push    r14
0x1400194c6  push    r15
0x1400194c8  lea     rbp, [rsp-130h]
0x1400194d0  sub     rsp, 230h
0x1400194d7  mov     rax, cs:__security_cookie
0x1400194de  xor     rax, rsp
0x1400194e1  mov     [rbp+160h+var_40], rax
0x1400194e8  mov     rax, [rbp+160h+arg_30]
0x1400194ef  mov     r15, r9
0x1400194f2  mov     r14, [rbp+160h+arg_20]
0x1400194f9  xor     edi, edi
0x1400194fb  mov     rsi, [rbp+160h+arg_28]
0x140019502  xorps   xmm1, xmm1
0x140019505  mov     [r9], edi
0x140019508  xorps   xmm0, xmm0
0x14001950b  mov     [rbp+160h+var_1C8], r9
0x14001950f  mov     r10, r8
0x140019512  mov     [rbp+160h+var_1D0], rax
0x140019516  mov     r13, rdx
0x140019519  mov     rax, [r8+20h]
0x14001951d  mov     [rsp+260h+var_208], r8
0x140019522  mov     r9d, [rax+50h]
0x140019526  shr     r9d, 11h
0x14001952a  movd    eax, xmm1
0x14001952e  not     r9d
0x140019531  movdqa  [rbp+160h+var_1B0], xmm1
0x140019536  and     r9d, 1
0x14001953a  or      r9d, 8
0x14001953e  movdqa  xmmword ptr [rbp+160h+var_1A0], xmm0
0x140019543  or      eax, 3
0x140019546  mov     [rbp+160h+var_190], rdi
0x14001954a  mov     dword ptr [rbp+160h+var_1B0], eax
0x14001954d  mov     rax, [r14+8]
0x140019551  mov     [rbp+160h+var_188], rdi
0x140019555  movdqa  [rbp+160h+var_180], xmm0
0x14001955a  cmp     dword ptr [rax+1Ch], 2
0x14001955e  jnz     short loc_14001956A
0x140019560  mov     rax, [rax+20h]
0x140019564  mov     rcx, [rax+10h]
0x140019568  jmp     short loc_140019575
0x14001956a  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140019571  mov     rcx, [rax+50h]
0x140019575  mov     r8, [r14]
0x140019578  lea     rax, [rbp+160h+var_1B0]
0x14001957c  mov     rdx, [r10+18h]
0x140019580  mov     [rsp+260h+var_230], r13
0x140019585  mov     [rsp+260h+var_238], rsi; char *
0x14001958a  mov     [rsp+260h+var_240], rax
0x14001958f  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140019594  mov     ebx, eax
0x140019596  test    eax, eax
0x140019598  jns     short loc_1400195C6
0x14001959a  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x1400195a1  mov     r8, 22000020571h; struct UnionFs::StackEventTracer *
0x1400195ab  lea     r9, aUnionfsUnionfs_59; "UnionFs::UnionFsFilter::PreCreateFileSu"...
0x1400195b2  mov     [rsp+260h+var_240], rax; char *
0x1400195b7  mov     rdx, rsi; int
0x1400195ba  mov     ecx, ebx; this
0x1400195bc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400195c1  jmp     loc_14001A14D
0x1400195c6  mov     eax, dword ptr [rbp+160h+var_1B0+4]
0x1400195c9  xor     ebx, ebx
0x1400195cb  mov     [rsp+260h+P], rbx
0x1400195d0  mov     [rsp+260h+var_200], ebx
0x1400195d4  lea     r8d, [rbx+4]
0x1400195d8  test    eax, eax
0x1400195da  jz      loc_14001998A
0x1400195e0  test    byte ptr [rbp+160h+var_1B0+8], r8b
0x1400195e4  jz      short loc_140019652
0x1400195e6  lea     edx, [rbx+1]
0x1400195e9  cmp     eax, edx
0x1400195eb  jnz     short loc_14001963B
0x1400195ed  mov     rax, [r13+10h]
0x1400195f1  mov     ecx, [rax+20h]
0x1400195f4  test    dl, cl
0x1400195f6  jz      short loc_140019604
0x1400195f8  lea     rcx, aFlagonCbdIopbP; "!FlagOn(Cbd.Iopb->Parameters.Create.Opt"...
0x1400195ff  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140019604  mov     rax, [rbp+160h+var_1A0+8]
0x140019608  xor     r15d, r15d
0x14001960b  mov     rcx, [rbp+160h+var_1A0]
0x14001960f  test    rax, rax
0x140019612  jz      short loc_140019618
0x140019614  lock inc dword ptr [rax+8]
0x140019618  mov     [r14+0A8h], rcx
0x14001961f  mov     rcx, [r14+0B0h]
0x140019626  mov     [r14+0B0h], rax
0x14001962d  test    rcx, rcx
0x140019630  jz      loc_14001A14A
0x140019636  jmp     loc_14001A145
0x14001963b  mov     dword ptr [r13+18h], 0C000003Ah
0x140019643  mov     [r13+20h], rbx
0x140019647  mov     [r15], r8d
0x14001964a  xor     r15d, r15d
0x14001964d  jmp     loc_14001A14A
0x140019652  mov     r12d, 1
0x140019658  cmp     dword ptr [rbp+160h+var_188], r12d
0x14001965c  jnz     short loc_14001966D
0x14001965e  mov     rax, [r14+0A0h]
0x140019665  or      dword ptr [rax], 8
0x140019668  jmp     loc_14001A14D
0x14001966d  mov     rax, [rbp+160h+var_1A0]
0x140019671  movzx   ecx, word ptr [rax+0A8h]
0x140019678  nop
0x140019679  cmp     cx, r8w
0x14001967d  jnz     short loc_1400196EB
0x14001967f  mov     rax, [rbp+160h+var_1A0]
0x140019683  cmp     [rax+0D8h], rbx
0x14001968a  jnz     short loc_140019698
0x14001968c  lea     rcx, aResultsCacheen; "results.CacheEntry->GetOriginalScratchP"...
0x140019693  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140019698  cmp     dword ptr [rbp+160h+var_1B0+4], r12d
0x14001969c  jnz     loc_14001994F
0x1400196a2  mov     rax, [r13+10h]
0x1400196a6  mov     ecx, [rax+20h]
0x1400196a9  test    cl, 40h
0x1400196ac  jnz     short loc_1400196BA
0x1400196ae  lea     rcx, aFailingSuperse; "Failing supersede on exact match for re"...
0x1400196b5  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400196ba  lea     rax, aOriginAttemptT; "ORIGIN: Attempt to supersede a director"...
0x1400196c1  mov     ebx, 0C00000BAh
0x1400196c6  mov     ecx, ebx; this
0x1400196c8  mov     [rsp+260h+var_240], rax; char *
0x1400196cd  lea     r9, aUnionfsUnionfs_59; "UnionFs::UnionFsFilter::PreCreateFileSu"...
0x1400196d4  mov     r8, 387000205AEh; struct UnionFs::StackEventTracer *
0x1400196de  mov     rdx, rsi; int
0x1400196e1  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400196e6  jmp     loc_14001A14D
0x1400196eb  cmp     dword ptr [rbp+160h+var_1B0+4], r12d
0x1400196ef  jnz     loc_14001994F
0x1400196f5  mov     rax, [rbp+160h+var_1A0]
0x1400196f9  mov     rdi, [rax+28h]
0x1400196fd  mov     r12, [rax+20h]
0x140019701  mov     [rsp+260h+P], r12
0x140019706  test    rdi, rdi
0x140019709  jz      short loc_14001970F
0x14001970b  lock inc dword ptr [rdi+8]
0x14001970f  xor     edx, edx; Val
0x140019711  lea     rcx, [rbp+160h+var_90]; void *
0x140019718  lea     r8d, [rdx+48h]; Size
0x14001971c  call    memset
0x140019721  call    cs:__imp_PsGetHostSilo
0x140019728  nop     dword ptr [rax+rax+00h]
0x14001972d  mov     rcx, [r12+8]
0x140019732  mov     r9d, 4
0x140019738  mov     [rsp+260h+var_230], rsi
0x14001973d  mov     r8, rax
0x140019740  mov     [rsp+260h+var_238], r13; char *
0x140019745  mov     r10, [rcx]
0x140019748  mov     rcx, [rbp+160h+var_1A0]
0x14001974c  mov     rdx, [rcx+30h]
0x140019750  lea     rcx, [rbp+160h+var_90]
0x140019757  mov     [rsp+260h+var_240], rcx
0x14001975c  lea     rcx, [rsp+260h+Resource]
0x140019761  movups  xmm0, xmmword ptr [rdx]
0x140019764  mov     rdx, r10
0x140019767  movdqu  xmmword ptr [rsp+260h+Resource], xmm0
0x14001976d  call    ?StatItemAsCaller@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::StatItemAsCaller(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x140019772  xor     r12d, r12d
0x140019775  mov     ebx, eax
0x140019777  test    eax, eax
0x140019779  jns     short loc_1400197B8
0x14001977b  lea     rax, aPushStatLayerI; "PUSH: Stat layer item"
0x140019782  mov     r8, 221000205CAh; struct UnionFs::StackEventTracer *
0x14001978c  lea     r9, aUnionfsUnionfs_59; "UnionFs::UnionFsFilter::PreCreateFileSu"...
0x140019793  mov     [rsp+260h+var_240], rax; char *
0x140019798  mov     rdx, rsi; int
0x14001979b  mov     ecx, ebx; this
0x14001979d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400197a2  test    rdi, rdi
0x1400197a5  jz      loc_14001A14D
0x1400197ab  mov     rcx, rdi; this
0x1400197ae  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400197b3  jmp     loc_14001A14D
0x1400197b8  cmp     ebx, 104h
0x1400197be  jnz     short loc_1400197D7
0x1400197c0  test    rdi, rdi
0x1400197c3  jz      short loc_1400197CD
0x1400197c5  mov     rcx, rdi; this
0x1400197c8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400197cd  mov     ebx, 104h
0x1400197d2  jmp     loc_14001A14D
0x1400197d7  mov     rbx, [rbp+160h+var_1A0]
0x1400197db  mov     eax, [rbp+160h+var_4C]
0x1400197e1  mov     [rsp+260h+var_200], eax
0x1400197e5  mov     rcx, [rbx+48h]; Context
0x1400197e9  call    cs:__imp_FltReferenceContext
0x1400197f0  nop     dword ptr [rax+rax+00h]
0x1400197f5  mov     rax, [rbx+48h]
0x1400197f9  lea     rcx, [rsp+260h+Resource]
0x1400197fe  mov     [rbp+160h+Context], rax
0x140019802  mov     rbx, [rax+20h]
0x140019806  mov     rdx, [rbx+78h]
0x14001980a  add     rdx, 38h ; '8'
0x14001980e  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140019813  mov     rax, [r13+10h]
0x140019817  lea     r9, [rbp+160h+Context]
0x14001981b  mov     [rsp+260h+var_220], rsi
0x140019820  mov     rdx, r13
0x140019823  mov     [rsp+260h+var_228], r14
0x140019828  mov     [rbp+160h+var_15C], r12b
0x14001982c  mov     rcx, [rax+18h]
0x140019830  mov     [rsp+260h+var_210], r12b
0x140019835  mov     r12, [rsp+260h+var_208]
0x14001983a  mov     rax, [rcx+8]
0x14001983e  mov     ecx, [rax+18h]
0x140019841  xor     eax, eax
0x140019843  mov     word ptr [rbp+160h+var_170.Buffer+5], ax
0x140019847  bts     ecx, 10h
0x14001984b  mov     byte ptr [rbp+160h+var_170.Buffer+7], al
0x14001984e  mov     [rbp+160h+var_15B], ax
0x140019852  mov     [rbp+160h+var_159], al
0x140019855  mov     eax, 1
0x14001985a  mov     dword ptr [rbp+160h+var_170+4], eax
0x14001985d  mov     byte ptr [rbp+160h+var_170.Buffer+4], al
0x140019860  mov     dword ptr [rbp+160h+var_170.Length], ecx
0x140019863  lea     r8d, [rax+1]
0x140019867  mov     dword ptr [rbp+160h+var_170.Buffer], ecx
0x14001986a  lea     rax, [rsp+260h+var_210]
0x14001986f  mov     [rbp+160h+var_160], r8d
0x140019873  mov     [rsp+260h+var_230], rax
0x140019878  mov     r8, r12
0x14001987b  lea     rax, [rbp+160h+var_170]
0x14001987f  mov     [rsp+260h+var_238], rbx; char *
0x140019884  mov     [rsp+260h+var_240], rax
0x140019889  call    ?CheckOplockAndShareAccess@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@$$QEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBUCheckOplockAndShareAccessParams@12@AEAVUfsFsContext@2@PEA_NAEAUCreateContext@2@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::CheckOplockAndShareAccess(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &&,UnionFs::UnionFsFilter::CheckOplockAndShareAccessParams const &,UnionFs::UfsFsContext &,bool *,UnionFs::CreateContext &,UnionFs::StackEventTracer &)
0x14001988e  mov     ebx, eax
0x140019890  test    eax, eax
0x140019892  jns     short loc_1400198FB
0x140019894  lea     rax, aPushOplockAndS; "PUSH: Oplock and share access check"
0x14001989b  mov     r8, 6E4000205FAh; struct UnionFs::StackEventTracer *
0x1400198a5  lea     r9, aUnionfsUnionfs_59; "UnionFs::UnionFsFilter::PreCreateFileSu"...
0x1400198ac  mov     [rsp+260h+var_240], rax; char *
0x1400198b1  mov     rdx, rsi; int
0x1400198b4  mov     ecx, ebx; this
0x1400198b6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400198bb  mov     rcx, [rsp+260h+Resource]; Resource
0x1400198c0  test    rcx, rcx
0x1400198c3  jz      short loc_1400198DD
0x1400198c5  call    cs:__imp_ExReleaseResourceLite
0x1400198cc  nop     dword ptr [rax+rax+00h]
0x1400198d1  call    cs:__imp_KeLeaveCriticalRegion
0x1400198d8  nop     dword ptr [rax+rax+00h]
0x1400198dd  mov     rcx, [rbp+160h+Context]; Context
0x1400198e1  test    rcx, rcx
0x1400198e4  jz      loc_1400197A2
0x1400198ea  call    cs:__imp_FltReleaseContext
0x1400198f1  nop     dword ptr [rax+rax+00h]
0x1400198f6  jmp     loc_1400197A2
0x1400198fb  cmp     ebx, 103h
0x140019901  jnz     short loc_14001990E
0x140019903  mov     dword ptr [r15], 2
0x14001990a  xor     ebx, ebx
0x14001990c  jmp     short loc_1400198BB
0x14001990e  xor     ebx, ebx
0x140019910  cmp     [rsp+260h+var_210], bl
0x140019914  jnz     short loc_1400198BB
0x140019916  mov     rcx, [rsp+260h+Resource]; Resource
0x14001991b  test    rcx, rcx
0x14001991e  jz      short loc_140019938
0x140019920  call    cs:__imp_ExReleaseResourceLite
0x140019927  nop     dword ptr [rax+rax+00h]
0x14001992c  call    cs:__imp_KeLeaveCriticalRegion
0x140019933  nop     dword ptr [rax+rax+00h]
0x140019938  mov     rcx, [rbp+160h+Context]; Context
0x14001993c  test    rcx, rcx
0x14001993f  jz      short loc_14001998F
0x140019941  call    cs:__imp_FltReleaseContext
0x140019948  nop     dword ptr [rax+rax+00h]
0x14001994d  jmp     short loc_14001998F
0x14001994f  mov     rcx, [rbp+160h+var_190]; Resource
0x140019953  mov     [rbp+160h+var_190], rbx
0x140019957  test    rcx, rcx
0x14001995a  jz      short loc_140019974
0x14001995c  call    cs:__imp_ExReleaseResourceLite
0x140019963  nop     dword ptr [rax+rax+00h]
0x140019968  call    cs:__imp_KeLeaveCriticalRegion
0x14001996f  nop     dword ptr [rax+rax+00h]
0x140019974  mov     rcx, [rbp+160h+var_1A0+8]; this
0x140019978  mov     [rbp+160h+var_1A0+8], rbx
0x14001997c  mov     [rbp+160h+var_1A0], rbx
0x140019980  test    rcx, rcx
0x140019983  jz      short loc_14001998A
0x140019985  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001998a  mov     r12, [rsp+260h+var_208]
0x14001998f  cmp     dword ptr [rbp+160h+var_188], 2
0x140019993  mov     [rbp+160h+Context], rbx
0x140019997  jnz     loc_140019A50
0x14001999d  mov     rax, qword ptr [rbp+160h+var_180+8]
0x1400199a1  lea     r8, [rsp+260h+Resource]; Source
0x1400199a6  mov     rcx, [r14]
0x1400199a9  lea     rdx, [rbp+160h+var_170]; struct _UNICODE_STRING *
0x1400199ad  add     rcx, 8; this
0x1400199b1  mov     [rsp+260h+var_238], rsi; char *
  ... truncated ...
```
