# UnionFs::UnionFsFilter::PreCreateFileOverwriteIf(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x1400183cc`
- end: `0x1400194af`
- name: `?PreCreateFileOverwriteIf@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `4323`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140011e20`

## callees

- `0x140002354`
- `0x14000c1dc`
- `0x14000efa0`
- `0x14000f81c`
- `0x140010ba8`
- `0x140010e30`
- `0x1400111b8`
- `0x1400114e4`
- `0x1400183cc`
- `0x14003cea8`
- `0x140041b30`
- `0x140043a64`
- `0x140043afc`
- `0x140044074`
- `0x140056c44`
- `0x140056c7c`
- `0x140061058`
- `0x14006127c`
- `0x14006be98`
- `0x1400704d4`
- `0x1400782bc`
- `0x14007862c`
- `0x140079d8c`
- `0x140079f68`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140018947`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400189c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018be3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018cae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018e34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018e63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001907b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400191aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019457`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018947`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400189c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018be3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018cae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018e34`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018e63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001907b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400191aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019457`
- `ntoskrnl!PsGetHostSilo` at `0x1400185e0`
- `ntoskrnl!PsGetHostSilo` at `0x1400185e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018787`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400187e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001882d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001886d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019209`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018787`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400187e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001882d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001886d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019209`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018793`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400187ee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018839`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018879`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019215`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018793`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400187ee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018839`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018879`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019215`
- `FLTMGR!FltReferenceContext` at `0x1400186a5`
- `FLTMGR!FltReferenceContext` at `0x1400186a5`
- `FLTMGR!FltReleaseContext` at `0x1400187ad`
- `FLTMGR!FltReleaseContext` at `0x14001880b`
- `FLTMGR!FltReleaseContext` at `0x140018852`
- `FLTMGR!FltReleaseContext` at `0x1400187ad`
- `FLTMGR!FltReleaseContext` at `0x14001880b`
- `FLTMGR!FltReleaseContext` at `0x140018852`

## string_xrefs

- `0x1400184b0`: `PUSH: Cache lookup`
- `0x140018564`: `results.CacheEntry->GetOriginalScratchPath()`
- `0x14001897d`: `PUSH: Allocating scratch path for layer lookup`
- `0x14001851c`: `!FlagOn(Cbd.Iopb->Parameters.Create.Options, FILE_DIRECTORY_FILE)`
- `0x140018757`: `PUSH: Oplock and share access check`
- `0x140018df2`: `PUSH: Preparing for scratch create`
- `0x1400190cb`: `!layer && !fullPathInLayer`
- `0x1400185a7`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018669`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018768`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x14001890c`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018aff`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018baa`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018c48`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018e03`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018f59`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x14001903d`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140019156`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140019285`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140019369`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018588`: `Failing overwrite_if on exact match for renamed tombstone`
- `0x140018594`: `ORIGIN: Attempt to overwrite_if a directory by opening it as a non-directory`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCreateFileOverwriteIf(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        enum _FLT_PREOP_CALLBACK_STATUS *a4,
        struct UnionFs::CreateContext *a5,
        struct UnionFs::StackEventTracer *a6,
        const struct UnionFs::UfsSiloCtx *a7)
{
  PFILE_OBJECT FileObject; // rax
  ULONG v11; // r9d
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // ebx
  __int64 v16; // r8
  const char *v17; // rax
  __int64 v18; // r8
  char v19; // r12
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int *HostSilo; // r8
  utl::_RefCountBase *v23; // rax
  volatile signed __int32 *v24; // rdi
  __int64 v25; // rcx
  __int64 v26; // rdx
  utl::_RefCountBase *v27; // rbx
  struct UnionFs::UfsStreamHandleCtx *v28; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  __int64 v31; // rcx
  struct _ERESOURCE *v32; // rcx
  utl::_RefCountBase *v33; // rcx
  UnionFs::Rtl *v34; // rcx
  struct _UNICODE_STRING *v35; // rdx
  int v36; // edi
  const char *v37; // rax
  __int64 v38; // r8
  struct _UNICODE_STRING *v39; // rdx
  struct _UNICODE_STRING *v40; // rbx
  PFLT_CONTEXT v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rbx
  const struct UnionFs::UfsLayerCtx *v44; // r13
  volatile signed __int32 *v45; // rdi
  __int64 v46; // rdx
  int v47; // r8d
  char v48; // bl
  char v49; // r12
  __int64 v50; // r8
  struct _UNICODE_STRING *v51; // rdx
  int IsFileCowable; // r12d
  __int16 v53; // ax
  unsigned __int16 v54; // ax
  __int64 v55; // rcx
  struct _UNICODE_STRING *v56; // rdx
  struct _UNICODE_STRING *v57; // rbx
  char v58; // r12
  char *v59; // rbx
  struct _UNICODE_STRING *v60; // rdx
  struct _UNICODE_STRING *v61; // rbx
  __int64 v62; // rcx
  int v63; // eax
  utl::_RefCountBase *v64; // rcx
  utl::_RefCountBase *v65; // rcx
  struct _UNICODE_STRING *v66; // rbx
  void *v67; // rcx
  __int16 v68; // ax
  _DWORD *v69; // rax
  utl::_RefCountBase *v70; // rcx
  int v71; // r14d
  struct _UNICODE_STRING *v72; // rdx
  utl::_RefCountBase *v73; // rcx
  struct _UNICODE_STRING *v74; // rbx
  bool v75; // zf
  utl::_RefCountBase *v76; // rcx
  int v77; // r8d
  struct _UNICODE_STRING *v78; // rdx
  struct _UNICODE_STRING *v79; // rbx
  bool v80; // al
  struct _UNICODE_STRING *v81; // rdx
  struct _UNICODE_STRING *v82; // rbx
  volatile signed __int32 *v83; // r12
  utl::_RefCountBase *v84; // rcx
  __int64 v85; // r8
  __int64 v86; // rax
  struct _UNICODE_STRING *v87; // rdx
  struct _UNICODE_STRING *v88; // rbx
  utl::_RefCountBase *v89; // rax
  utl::_RefCountBase *v90; // rcx
  utl::_RefCountBase *v91; // rcx
  struct _ERESOURCE *v92; // rcx
  struct _FLT_RELATED_OBJECTS *v93; // rbx
  utl::_RefCountBase *v94; // rcx
  utl::_RefCountBase *v95; // rax
  utl::_RefCountBase *v96; // rcx
  struct _UNICODE_STRING *v97; // rdx
  struct _UNICODE_STRING *v98; // rdx
  _DWORD *v99; // rax
  struct _UNICODE_STRING *v100; // rbx
  struct UnionFs::UfsStreamHandleCtx *v102; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v103; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v104; // [rsp+28h] [rbp-D8h]
  struct UnionFs::UfsStreamHandleCtx *v105; // [rsp+28h] [rbp-D8h]
  char v106; // [rsp+50h] [rbp-B0h] BYREF
  char v107; // [rsp+51h] [rbp-AFh]
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  PFLT_CONTEXT Context[2]; // [rsp+60h] [rbp-A0h] BYREF
  PVOID v110[2]; // [rsp+70h] [rbp-90h] BYREF
  int v111; // [rsp+80h] [rbp-80h]
  char v112; // [rsp+84h] [rbp-7Ch]
  __int16 v113; // [rsp+85h] [rbp-7Bh]
  char v114; // [rsp+87h] [rbp-79h]
  int v115; // [rsp+88h] [rbp-78h]
  PERESOURCE Resource[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v117; // [rsp+A0h] [rbp-60h] BYREF
  utl::_RefCountBase *v118[2]; // [rsp+B0h] [rbp-50h] BYREF
  PERESOURCE v119; // [rsp+C0h] [rbp-40h]
  __int64 v120; // [rsp+C8h] [rbp-38h]
  __int128 v121; // [rsp+D0h] [rbp-30h]
  struct _FLT_RELATED_OBJECTS *v122; // [rsp+E0h] [rbp-20h]
  _QWORD v123[2]; // [rsp+E8h] [rbp-18h] BYREF
  struct UnionFs::UfsSiloCtx *v124; // [rsp+F8h] [rbp-8h]
  char v125[8]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v126; // [rsp+108h] [rbp+8h]
  utl::_RefCountBase *v127[2]; // [rsp+118h] [rbp+18h]
  __int64 v128; // [rsp+128h] [rbp+28h]
  int v129; // [rsp+130h] [rbp+30h]
  struct _UNICODE_STRING UnicodeString; // [rsp+140h] [rbp+40h] BYREF
  char v131; // [rsp+150h] [rbp+50h]
  PWSTR *p_Buffer; // [rsp+1B0h] [rbp+B0h]
  _OWORD v133[5]; // [rsp+1C0h] [rbp+C0h] BYREF
  _DWORD v134[20]; // [rsp+210h] [rbp+110h] BYREF

  *a4 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
  v123[0] = a4;
  v124 = a7;
  FileObject = a3->FileObject;
  v122 = a3;
  v11 = FileObject->Flags >> 17;
  v117 = 0;
  v12 = ((v11 & 1) == 0) | 8u;
  *(_OWORD *)v118 = 0;
  v119 = 0;
  LODWORD(v117) = _mm_cvtsi128_si32((__m128i)0LL) | 3;
  v13 = *((_QWORD *)a5 + 1);
  v120 = 0;
  v121 = 0;
  if ( *(_DWORD *)(v13 + 28) == 2 )
    v14 = *(_QWORD *)(*(_QWORD *)(v13 + 32) + 16LL);
  else
    v14 = *((_QWORD *)UnionFs::g_FilterState + 10);
  v102 = a6;
  v15 = UnionFs::UfsPathCache::LookupEntry(v14, a3->Instance, *(_QWORD *)a5, v12, &v117);
  if ( v15 < 0 )
  {
    v17 = "PUSH: Cache lookup";
    v18 = 0x22700021006LL;
LABEL_28:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v15,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v18,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
      v17,
      (const char *)v102);
    goto LABEL_227;
  }
  v19 = 0;
  v115 = 0;
  v106 = 0;
  if ( !DWORD1(v117) )
    goto LABEL_51;
  if ( (BYTE8(v117) & 4) != 0 )
  {
    if ( DWORD1(v117) == 1 )
    {
      UnionFs::CreateContext::OverwriteTombstone(a5, v118, v16);
      if ( (a2->Iopb->Parameters.Create.Options & 1) != 0 )
        MicrosoftTelemetryAssertTriggeredMsgKM("!FlagOn(Cbd.Iopb->Parameters.Create.Options, FILE_DIRECTORY_FILE)");
    }
    else
    {
      a2->IoStatus.Status = -1073741766;
      a2->IoStatus.Information = 0;
      *a4 = FLT_PREOP_COMPLETE;
    }
    goto LABEL_226;
  }
  if ( (_DWORD)v120 == 1 )
  {
    **((_DWORD **)a5 + 20) |= 8u;
LABEL_226:
    v15 = 0;
    goto LABEL_227;
  }
  if ( *((_WORD *)v118[0] + 84) == 4 )
  {
    if ( !*((_QWORD *)v118[0] + 27) )
      MicrosoftTelemetryAssertTriggeredMsgKM("results.CacheEntry->GetOriginalScratchPath()");
    if ( DWORD1(v117) == 1 )
    {
      if ( (a2->Iopb->Parameters.Create.Options & 0x40) == 0 )
        MicrosoftTelemetryAssertTriggeredMsgKM("Failing overwrite_if on exact match for renamed tombstone");
      v15 = -1073741638;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC00000BALL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x38900021055LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
        "ORIGIN: Attempt to overwrite_if a directory by opening it as a non-directory",
        (const char *)a6);
      goto LABEL_227;
    }
    goto LABEL_47;
  }
  if ( DWORD1(v117) != 1 )
  {
LABEL_47:
    v32 = v119;
    v119 = 0;
    if ( v32 )
    {
      ExReleaseResourceLite(v32);
      KeLeaveCriticalRegion();
    }
    v33 = v118[1];
    v118[1] = 0;
    v118[0] = 0;
    if ( v33 )
      utl::_RefCountBase::_DecStrong(v33);
LABEL_51:
    Context[0] = 0;
    if ( (_DWORD)v120 != 2 )
      goto LABEL_61;
    v34 = (UnionFs::Rtl *)(*(_QWORD *)a5 + 8LL);
    *(_OWORD *)v110 = **((_OWORD **)&v121 + 1);
    *(_OWORD *)Resource = *(_OWORD *)v121;
    v36 = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(
            v34,
            (struct _UNICODE_STRING *)Resource,
            (PCUNICODE_STRING)v110,
            Context,
            (int)a6);
    if ( v36 < 0 )
    {
      v37 = "PUSH: Replacing substring";
      v38 = 0x384000210D1LL;
LABEL_54:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v36,
        (int)a6,
        (struct UnionFs::StackEventTracer *)v38,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
        v37,
        (const char *)v102);
      v40 = (struct _UNICODE_STRING *)Context[0];
LABEL_55:
      if ( v40 )
      {
        if ( !LOBYTE(v40[1].Length) )
          *v40 = 0;
        FsFltWil::Details::FreeUnicodeString(v40, v39);
        ExFreePoolWithTag(v40, 0);
      }
LABEL_59:
      v15 = v36;
      goto LABEL_227;
    }
    v41 = Context[0];
    if ( !Context[0] )
    {
LABEL_61:
      v36 = UnionFs::UfsPathName::AllocAndInit(*(_QWORD *)a5, Context, a6);
      if ( v36 < 0 )
      {
        v37 = "PUSH: Allocating scratch path for layer lookup";
        v38 = 0x397000210DCLL;
        goto LABEL_54;
      }
      v41 = Context[0];
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
    if ( v19 && !DWORD1(v117) )
      MicrosoftTelemetryAssertTriggeredMsgKM("!needsCow || (results.LookupResult != MAPPING_LOOKUP_RESULT::None)");
    v44 = 0;
    v110[0] = 0;
    v45 = 0;
    P = 0;
    v46 = 0;
    Resource[0] = 0;
    if ( v118[0] )
    {
      v47 = v115;
      v48 = 0;
      v49 = v106;
      goto LABEL_144;
    }
    UnicodeString.Buffer = (PWSTR)off_14007E748;
    p_Buffer = &UnicodeString.Buffer;
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(a6, &UnicodeString);
    memset(v133, 0, 0x48u);
    v102 = a6;
    IsFileCowable = UnionFs::Utils::StatItemAsCaller(*(_QWORD *)a5 + 8LL, v122->Instance, v50, v133, a2);
    v53 = *((_WORD *)a6 + 245);
    if ( v53 )
    {
      v54 = v53 - 1;
      *((_WORD *)a6 + 245) = v54;
      v51 = (struct _UNICODE_STRING *)(120 * (v54 + 1LL));
      v55 = *(_QWORD *)((char *)a6 + (_QWORD)v51);
      *(_QWORD *)((char *)a6 + (_QWORD)v51) = 0;
      if ( v55 )
        (*(void (__fastcall **)(__int64, struct _UNICODE_STRING *, __int64))(*(_QWORD *)v55 + 24LL))(v55, v51, 1);
    }
    if ( IsFileCowable == 260 )
      goto LABEL_107;
    if ( IsFileCowable >= 0 || IsFileCowable == -1073741766 )
    {
      v107 = 0;
      if ( IsFileCowable != -1073741766 )
      {
        v49 = v106;
        v48 = 0;
        v46 = 0;
        goto LABEL_143;
      }
      v58 = 0;
    }
    else
    {
      if ( IsFileCowable != -1073741772 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)IsFileCowable,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0xFA00021105LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
          "PUSH: Querying stat information",
          (const char *)a6);
        v57 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v57, v56);
          ExFreePoolWithTag(v57, 0);
        }
        goto LABEL_84;
      }
      v58 = 1;
      v107 = 1;
    }
    utl::make_unique<UnionFs::FindAndStatResults,,0>(v110);
    v59 = (char *)v110[0];
    if ( !v110[0] )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x40200021114LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
        "ORIGIN: Allocating findAndStatResults",
        (const char *)a6);
      v61 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v61, v60);
        ExFreePoolWithTag(v61, 0);
      }
      v15 = -1073741670;
      goto LABEL_227;
    }
    *((_QWORD *)v110[0] + 12) = &P;
    v62 = *((_QWORD *)a5 + 1);
    v102 = (struct UnionFs::UfsStreamHandleCtx *)v59;
    *(_OWORD *)v110 = *(_OWORD *)*(_QWORD *)(*((_QWORD *)a5 + 20) + 64LL);
    v63 = UnionFs::UfsUnionCtx::FindAndStatItemInLayersAsCaller(v62, a2, v110);
    v36 = v63;
    if ( v63 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v63,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0xFB0002111FLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
        "PUSH: Probing for item in layers",
        v59);
      if ( v59 )
      {
        v64 = (utl::_RefCountBase *)*((_QWORD *)v59 + 11);
        if ( v64 )
          utl::_RefCountBase::_DecStrong(v64);
        ExFreePoolWithTag(v59, 0);
      }
      v40 = (struct _UNICODE_STRING *)P;
      goto LABEL_55;
    }
    if ( v63 == 260 )
    {
      if ( v59 )
      {
        v65 = (utl::_RefCountBase *)*((_QWORD *)v59 + 11);
        if ( v65 )
          utl::_RefCountBase::_DecStrong(v65);
        ExFreePoolWithTag(v59, 0);
      }
LABEL_107:
      v66 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v66, v51);
        ExFreePoolWithTag(v66, 0);
      }
      v15 = 260;
      goto LABEL_227;
    }
    v133[0] = *(_OWORD *)(v59 + 8);
    v133[1] = *(_OWORD *)(v59 + 24);
    v133[2] = *(_OWORD *)(v59 + 40);
    v133[3] = *(_OWORD *)(v59 + 56);
    *(_QWORD *)&v133[4] = *((_QWORD *)v59 + 9);
    v45 = (volatile signed __int32 *)*((_QWORD *)v59 + 11);
    v67 = (void *)*((_QWORD *)v59 + 10);
    v110[0] = v67;
    if ( v45 )
      _InterlockedIncrement(v45 + 2);
    v68 = *(_WORD *)v59;
    v46 = 2;
    if ( *(_WORD *)v59 == 2 )
    {
      if ( !v58 )
      {
        v69 = (_DWORD *)v123[0];
        a2->IoStatus.Status = -1073741766;
        a2->IoStatus.Information = 0;
        *v69 = 4;
      }
LABEL_117:
      if ( v59 )
      {
        v70 = (utl::_RefCountBase *)*((_QWORD *)v59 + 11);
        if ( v70 )
          utl::_RefCountBase::_DecStrong(v70);
        ExFreePoolWithTag(v59, 0);
      }
      goto LABEL_220;
    }
    v46 = 3;
    if ( v68 == 3 )
    {
      if ( !v58 )
      {
        v71 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
                *((UnionFs::UfsUnionCtx **)a5 + 1),
                a2,
                v122,
                *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
                *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
                *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
                (const struct UnionFs::UfsLayerCtx *)v67,
                a6,
                v124);
        if ( v71 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v71,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x7C0002114BLL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
            "PUSH: Preparing for scratch create",
            (const char *)v103);
          if ( v59 )
          {
            v73 = (utl::_RefCountBase *)*((_QWORD *)v59 + 11);
            if ( v73 )
              utl::_RefCountBase::_DecStrong(v73);
            ExFreePoolWithTag(v59, 0);
          }
          v74 = (struct _UNICODE_STRING *)P;
          if ( !P )
            goto LABEL_133;
          v75 = *((_BYTE *)P + 16) == 0;
          goto LABEL_130;
        }
      }
      goto LABEL_117;
    }
    v49 = 1;
    if ( v68 != 1 )
      MicrosoftTelemetryAssertTriggeredMsgKM("findAndStatResults->FindResult == LAYER_FIND_RESULT::Found");
    v46 = *((unsigned int *)v59 + 16);
    Resource[0] = (PERESOURCE)P;
    LODWORD(Context[0]) = v46;
    if ( v59 )
    {
      v76 = (utl::_RefCountBase *)*((_QWORD *)v59 + 11);
      if ( v76 )
        utl::_RefCountBase::_DecStrong(v76);
      ExFreePoolWithTag(v59, 0);
      v46 = LODWORD(Context[0]);
    }
    v48 = v107;
LABEL_143:
    v47 = DWORD1(v133[4]);
    v44 = (const struct UnionFs::UfsLayerCtx *)v110[0];
LABEL_144:
    v77 = *(_DWORD *)(*(_QWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 8) + 20LL) | v47;
    if ( (v77 & 2) != 0 )
    {
      if ( v49 )
      {
        if ( (*(_DWORD *)(*((_QWORD *)a5 + 1) + 24LL) & 0x80u) != 0 )
        {
          v106 = 0;
          if ( v118[0] )
          {
            IsFileCowable = UnionFs::Utils::IsFileCowable((UnionFs::Utils *)&v106, (bool *)v118[0], a6, 0);
            if ( IsFileCowable < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)IsFileCowable,
                (int)a6,
                (struct UnionFs::StackEventTracer *)0x78800021177LL,
                (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
                "PUSH: Checking immutability",
                (const char *)v102);
LABEL_150:
              v79 = (struct _UNICODE_STRING *)P;
              if ( P )
              {
                if ( !*((_BYTE *)P + 16) )
                  *(_OWORD *)P = 0;
                FsFltWil::Details::FreeUnicodeString(v79, v78);
                ExFreePoolWithTag(v79, 0);
              }
              if ( v45 )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v45);
LABEL_84:
              v15 = IsFileCowable;
              goto LABEL_227;
            }
            v80 = v106;
          }
          else
          {
            v80 = (v46 & 0x800010) != 0;
          }
          if ( !v80 )
          {
            if ( (unsigned int)dword_14009E178 > 5
              && (qword_14009E188 & 0x400000000000LL) != 0
              && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
            {
              v110[0] = (PVOID)1;
              v123[0] = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                qword_14009E190,
                (unsigned int)byte_140095FED,
                v77,
                (unsigned int)v123,
                (__int64)v110);
            }
            UnionFs::ProcessTraceStatusOrigin(
              (UnionFs *)0xC0000022LL,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x78900021189LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
              "ORIGIN: Rejecting COW for immutable file",
              (const char *)v102);
            v82 = (struct _UNICODE_STRING *)P;
            if ( P )
            {
              if ( !*((_BYTE *)P + 16) )
                *(_OWORD *)P = 0;
              FsFltWil::Details::FreeUnicodeString(v82, v81);
              ExFreePoolWithTag(v82, 0);
            }
            if ( v45 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v45);
            v15 = -1073741790;
            goto LABEL_227;
          }
        }
        *(_OWORD *)Context = 0;
        v110[0] = Context;
        LOBYTE(v110[1]) = 1;
        if ( v118[0] )
        {
          if ( v44 || Resource[0] )
            MicrosoftTelemetryAssertTriggeredMsgKM("!layer && !fullPathInLayer");
          v83 = (volatile signed __int32 *)*((_QWORD *)v118[0] + 5);
          v44 = (const struct UnionFs::UfsLayerCtx *)*((_QWORD *)v118[0] + 4);
          if ( v83 )
            _InterlockedIncrement(v83 + 2);
          if ( v45 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v45);
          v84 = v118[0];
          v85 = v121;
          Resource[0] = *((PERESOURCE *)v118[0] + 6);
          v123[0] = *((_QWORD *)a5 + 1);
          v86 = *((_QWORD *)a5 + 2);
          v123[1] = v86;
          if ( v86 )
            _InterlockedIncrement((volatile signed __int32 *)(v86 + 8));
          v36 = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v84, v123, v85, 12, a6);
          if ( v36 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v36,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x420000211ACLL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
              "PUSH: ConvertToSoftTombstone for COW",
              (const char *)v102);
            wil::details::lambda_call__lambda_336cae7d7f612d7c8c66fed0413d03c1___::_lambda_call__lambda_336cae7d7f612d7c8c66fed0413d03c1___(v110);
            if ( Context[1] )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context[1]);
            v88 = (struct _UNICODE_STRING *)P;
            if ( P )
            {
              if ( !*((_BYTE *)P + 16) )
                *(_OWORD *)P = 0;
              FsFltWil::Details::FreeUnicodeString(v88, v87);
              ExFreePoolWithTag(v88, 0);
            }
            if ( v83 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v83);
            goto LABEL_59;
          }
          v89 = v118[1];
          v45 = v83;
          v90 = v118[0];
          if ( v118[1] )
            _InterlockedIncrement((volatile signed __int32 *)v118[1] + 2);
          Context[0] = v90;
          v91 = (utl::_RefCountBase *)Context[1];
          Context[1] = v89;
          if ( v91 )
            utl::_RefCountBase::_DecStrong(v91);
          v92 = v119;
          v119 = 0;
          if ( v92 )
          {
            ExReleaseResourceLite(v92);
            KeLeaveCriticalRegion();
          }
        }
        v75 = v48 == 0;
        v93 = v122;
        if ( v75 )
        {
          IsFileCowable = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
                            *((UnionFs::UfsUnionCtx **)a5 + 1),
                            a2,
                            v122,
                            *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
                            *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
                            *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
                            v44,
                            a6,
                            v124);
          if ( IsFileCowable < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)IsFileCowable,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x294000211C1LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
              "PUSH: Preparing for COW",
              (const char *)v104);
            wil::details::lambda_call__lambda_336cae7d7f612d7c8c66fed0413d03c1___::_lambda_call__lambda_336cae7d7f612d7c8c66fed0413d03c1___(v110);
            if ( Context[1] )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context[1]);
            goto LABEL_150;
          }
        }
        v94 = v118[0];
        *(_QWORD *)v125 = *((_QWORD *)a5 + 1);
        v95 = v118[1];
        v128 = 0;
        v129 = 22;
        v126 = 0;
        *(_OWORD *)v127 = 0;
        if ( v118[1] )
          _InterlockedIncrement((volatile signed __int32 *)v118[1] + 2);
        *((_QWORD *)&v126 + 1) = v94;
        v96 = v127[0];
        v127[0] = v95;
        if ( v96 )
          utl::_RefCountBase::_DecStrong(v96);
        UnionFs::UfsPathName::UfsPathName(
          (UnionFs::UfsPathName *)&UnicodeString,
          (const struct _UNICODE_STRING *)(*(_QWORD *)a5 + 8LL),
          *(_WORD *)(*(_QWORD *)a5 + 24LL));
        v71 = UnionFs::Utils::CopyItem(
                (_DWORD)a2,
                (_DWORD)v44,
                Resource[0],
                v93->Instance,
                &UnicodeString,
                (__int64)v125,
                (struct _FILE_OBJECT *)a6,
                0);
        if ( v71 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v71,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x293000211D3LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
            "PUSH: Performing COW",
            (const char *)v105);
          if ( !v131 )
            UnicodeString = 0;
          FsFltWil::Details::FreeUnicodeString(&UnicodeString, v98);
          if ( v127[0] )
            utl::_RefCountBase::_DecStrong(v127[0]);
          wil::details::lambda_call__lambda_336cae7d7f612d7c8c66fed0413d03c1___::_lambda_call__lambda_336cae7d7f612d7c8c66fed0413d03c1___(v110);
          if ( Context[1] )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context[1]);
          v74 = (struct _UNICODE_STRING *)P;
          if ( !P )
            goto LABEL_133;
          v75 = *((_BYTE *)P + 16) == 0;
LABEL_130:
          if ( v75 )
            *v74 = 0;
          FsFltWil::Details::FreeUnicodeString(v74, v72);
          ExFreePoolWithTag(v74, 0);
LABEL_133:
          if ( v45 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v45);
          v15 = v71;
          goto LABEL_227;
        }
        LOBYTE(v110[1]) = 0;
        if ( !v131 )
          UnicodeString = 0;
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v97);
        if ( v127[0] )
          utl::_RefCountBase::_DecStrong(v127[0]);
        wil::details::lambda_call__lambda_336cae7d7f612d7c8c66fed0413d03c1___::_lambda_call__lambda_336cae7d7f612d7c8c66fed0413d03c1___(v110);
        if ( Context[1] )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context[1]);
      }
    }
    else
    {
      v99 = (_DWORD *)v123[0];
      a2->IoStatus.Status = -1073741790;
      a2->IoStatus.Information = 0;
      *v99 = 4;
    }
LABEL_220:
    v100 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v100, (struct _UNICODE_STRING *)v46);
      ExFreePoolWithTag(v100, 0);
    }
    if ( v45 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v45);
    goto LABEL_226;
  }
  memset(v134, 0, 0x48u);
  HostSilo = (unsigned int *)PsGetHostSilo(v21, v20);
  v23 = v118[0];
  v24 = (volatile signed __int32 *)*((_QWORD *)v118[0] + 5);
  v25 = *((_QWORD *)v118[0] + 4);
  if ( v24 )
  {
    _InterlockedIncrement(v24 + 2);
    v23 = v118[0];
  }
  v26 = **(_QWORD **)(v25 + 8);
  *(_OWORD *)v110 = *(_OWORD *)*((_QWORD *)v23 + 6);
  v15 = UnionFs::Utils::StatItemAsCaller(
          (const char *)v110,
          v26,
          HostSilo,
          4,
          (__int64)v134,
          (UnionFs::Utils *)a2,
          (int)a6);
  if ( v24 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v24);
  if ( v15 < 0 )
  {
    v17 = "PUSH: Stat layer item";
    v18 = 0x2280002106FLL;
    goto LABEL_28;
  }
  if ( v15 == 260 )
  {
    v15 = 260;
    goto LABEL_227;
  }
  v27 = v118[0];
  v115 = v134[17];
  FltReferenceContext(*((PFLT_CONTEXT *)v118[0] + 9));
  Context[0] = *((PFLT_CONTEXT *)v27 + 9);
  v28 = (struct UnionFs::UfsStreamHandleCtx *)*((_QWORD *)Context[0] + 4);
  FsFltWil::AcquireResourceExclusive(Resource, *((_QWORD *)v28 + 15) + 56LL);
  Iopb = a2->Iopb;
  v112 = 0;
  SecurityContext = Iopb->Parameters.Create.SecurityContext;
  v111 = 12;
  v106 = 0;
  LODWORD(SecurityContext) = SecurityContext->AccessState->OriginalDesiredAccess;
  *(_WORD *)((char *)&v110[1] + 5) = 0;
  v31 = (unsigned int)SecurityContext | 2;
  HIBYTE(v110[1]) = 0;
  v113 = 0;
  v114 = 0;
  v110[0] = (PVOID)((unsigned int)v31 | 0xB00000000LL);
  v102 = v28;
  LODWORD(v110[1]) = v31;
  BYTE4(v110[1]) = 1;
  v15 = UnionFs::UnionFsFilter::CheckOplockAndShareAccess(v31, a2, a3, Context, v110);
  if ( v15 >= 0 )
  {
    if ( v15 == 259 )
    {
      *(_DWORD *)v123[0] = 2;
      if ( Resource[0] )
      {
        ExReleaseResourceLite(Resource[0]);
        KeLeaveCriticalRegion();
      }
      if ( Context[0] )
        FltReleaseContext(Context[0]);
      goto LABEL_226;
    }
    v19 = 1;
    v106 = 1;
    if ( Resource[0] )
    {
      ExReleaseResourceLite(Resource[0]);
      KeLeaveCriticalRegion();
    }
    if ( Context[0] )
      FltReleaseContext(Context[0]);
    goto LABEL_51;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v15,
    (int)a6,
    (struct UnionFs::StackEventTracer *)0x6EA0002109FLL,
    (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
    "PUSH: Oplock and share access check",
    (const char *)v102);
  if ( Resource[0] )
  {
    ExReleaseResourceLite(Resource[0]);
    KeLeaveCriticalRegion();
  }
  if ( Context[0] )
    FltReleaseContext(Context[0]);
LABEL_227:
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v117);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400183cc  mov     [rsp-8+arg_0], rbx
0x1400183d1  push    rbp
0x1400183d2  push    rsi
0x1400183d3  push    rdi
0x1400183d4  push    r12
0x1400183d6  push    r13
0x1400183d8  push    r14
0x1400183da  push    r15
0x1400183dc  lea     rbp, [rsp-170h]
0x1400183e4  sub     rsp, 270h
0x1400183eb  mov     rax, cs:__security_cookie
0x1400183f2  xor     rax, rsp
0x1400183f5  mov     [rbp+1A0h+var_40], rax
0x1400183fc  mov     rax, [rbp+1A0h+arg_30]
0x140018403  mov     rdi, r9
0x140018406  mov     r14, [rbp+1A0h+arg_20]
0x14001840d  xor     ecx, ecx
0x14001840f  mov     rsi, [rbp+1A0h+arg_28]
0x140018416  xorps   xmm1, xmm1
0x140018419  mov     [r9], ecx
0x14001841c  xorps   xmm0, xmm0
0x14001841f  mov     [rbp+1A0h+var_1B8], r9
0x140018423  mov     r13, r8
0x140018426  mov     [rbp+1A0h+var_1A8], rax
0x14001842a  mov     r15, rdx
0x14001842d  mov     rax, [r8+20h]
0x140018431  mov     [rbp+1A0h+var_1C0], r8
0x140018435  mov     r9d, [rax+50h]
0x140018439  shr     r9d, 11h
0x14001843d  movd    eax, xmm1
0x140018441  not     r9d
0x140018444  movdqa  [rbp+1A0h+var_200], xmm1
0x140018449  and     r9d, 1
0x14001844d  or      r9d, 8
0x140018451  movdqa  xmmword ptr [rbp+1A0h+var_1F0], xmm0
0x140018456  or      eax, 3
0x140018459  mov     [rbp+1A0h+var_1E0], rcx
0x14001845d  mov     dword ptr [rbp+1A0h+var_200], eax
0x140018460  mov     rax, [r14+8]
0x140018464  mov     [rbp+1A0h+var_1D8], rcx
0x140018468  movdqa  [rbp+1A0h+var_1D0], xmm0
0x14001846d  cmp     dword ptr [rax+1Ch], 2
0x140018471  jnz     short loc_14001847D
0x140018473  mov     rax, [rax+20h]
0x140018477  mov     rcx, [rax+10h]
0x14001847b  jmp     short loc_140018488
0x14001847d  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140018484  mov     rcx, [rax+50h]
0x140018488  mov     r8, [r14]
0x14001848b  lea     rax, [rbp+1A0h+var_200]
0x14001848f  mov     rdx, [r13+18h]
0x140018493  mov     [rsp+2A0h+var_270], r15
0x140018498  mov     [rsp+2A0h+var_278], rsi; char *
0x14001849d  mov     [rsp+2A0h+var_280], rax
0x1400184a2  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x1400184a7  xor     r9d, r9d
0x1400184aa  mov     ebx, eax
0x1400184ac  test    eax, eax
0x1400184ae  jns     short loc_1400184C6
0x1400184b0  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x1400184b7  mov     r8, 22700021006h
0x1400184c1  jmp     loc_140018669
0x1400184c6  mov     eax, dword ptr [rbp+1A0h+var_200+4]
0x1400184c9  mov     r12b, r9b
0x1400184cc  mov     [rbp+1A0h+var_218], r9d
0x1400184d0  mov     edx, 4
0x1400184d5  mov     [rsp+2A0h+var_250], r9b
0x1400184da  test    eax, eax
0x1400184dc  jz      loc_1400188A1
0x1400184e2  test    byte ptr [rbp+1A0h+var_200+8], dl
0x1400184e5  jz      short loc_14001852D
0x1400184e7  lea     ebx, [rdx-3]
0x1400184ea  cmp     eax, ebx
0x1400184ec  jz      short loc_140018501
0x1400184ee  mov     dword ptr [r15+18h], 0C000003Ah
0x1400184f6  mov     [r15+20h], r9
0x1400184fa  mov     [rdi], edx
0x1400184fc  jmp     loc_140019476
0x140018501  lea     rdx, [rbp+1A0h+var_1F0]
0x140018505  mov     rcx, r14
0x140018508  call    ?OverwriteTombstone@CreateContext@UnionFs@@QEAAX$$QEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@Z; UnionFs::CreateContext::OverwriteTombstone(utl::shared_ptr<UnionFs::UfsPathCachePayload> &&)
0x14001850d  mov     rax, [r15+10h]
0x140018511  mov     ecx, [rax+20h]
0x140018514  test    bl, cl
0x140018516  jz      loc_140019473
0x14001851c  lea     rcx, aFlagonCbdIopbP; "!FlagOn(Cbd.Iopb->Parameters.Create.Opt"...
0x140018523  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140018528  jmp     loc_140019473
0x14001852d  mov     edi, 1
0x140018532  cmp     dword ptr [rbp+1A0h+var_1D8], edi
0x140018535  jnz     short loc_140018546
0x140018537  mov     rax, [r14+0A0h]
0x14001853e  or      dword ptr [rax], 8
0x140018541  jmp     loc_140019476
0x140018546  mov     rax, [rbp+1A0h+var_1F0]
0x14001854a  movzx   ecx, word ptr [rax+0A8h]
0x140018551  nop
0x140018552  cmp     cx, dx
0x140018555  jnz     short loc_1400185C5
0x140018557  mov     rax, [rbp+1A0h+var_1F0]
0x14001855b  cmp     [rax+0D8h], r9
0x140018562  jnz     short loc_140018573
0x140018564  lea     rcx, aResultsCacheen; "results.CacheEntry->GetOriginalScratchP"...
0x14001856b  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140018570  xor     r9d, r9d
0x140018573  cmp     dword ptr [rbp+1A0h+var_200+4], edi
0x140018576  jnz     loc_140018860
0x14001857c  mov     rax, [r15+10h]
0x140018580  mov     ecx, [rax+20h]
0x140018583  test    cl, 40h
0x140018586  jnz     short loc_140018594
0x140018588  lea     rcx, aFailingOverwri_0; "Failing overwrite_if on exact match for"...
0x14001858f  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140018594  lea     rax, aOriginAttemptT_0; "ORIGIN: Attempt to overwrite_if a direc"...
0x14001859b  mov     ebx, 0C00000BAh
0x1400185a0  mov     ecx, ebx; this
0x1400185a2  mov     [rsp+2A0h+var_280], rax; char *
0x1400185a7  lea     r9, aUnionfsUnionfs_13; "UnionFs::UnionFsFilter::PreCreateFileOv"...
0x1400185ae  mov     r8, 38900021055h; struct UnionFs::StackEventTracer *
0x1400185b8  mov     rdx, rsi; int
0x1400185bb  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400185c0  jmp     loc_140019479
0x1400185c5  cmp     dword ptr [rbp+1A0h+var_200+4], edi
0x1400185c8  jnz     loc_140018860
0x1400185ce  xor     edx, edx; Val
0x1400185d0  lea     rcx, [rbp+1A0h+var_90]; void *
0x1400185d7  lea     r8d, [rdx+48h]; Size
0x1400185db  call    memset
0x1400185e0  call    cs:__imp_PsGetHostSilo
0x1400185e7  nop     dword ptr [rax+rax+00h]
0x1400185ec  mov     r8, rax
0x1400185ef  xor     r12d, r12d
0x1400185f2  mov     rax, [rbp+1A0h+var_1F0]
0x1400185f6  mov     rdi, [rax+28h]
0x1400185fa  mov     rcx, [rax+20h]
0x1400185fe  test    rdi, rdi
0x140018601  jz      short loc_14001860B
0x140018603  lock inc dword ptr [rdi+8]
0x140018607  mov     rax, [rbp+1A0h+var_1F0]
0x14001860b  mov     rax, [rax+30h]
0x14001860f  mov     r9d, 4
0x140018615  mov     rcx, [rcx+8]
0x140018619  mov     [rsp+2A0h+var_270], rsi
0x14001861e  mov     [rsp+2A0h+var_278], r15; char *
0x140018623  movups  xmm0, xmmword ptr [rax]
0x140018626  mov     rdx, [rcx]
0x140018629  lea     rax, [rbp+1A0h+var_90]
0x140018630  lea     rcx, [rsp+2A0h+var_230]
0x140018635  mov     [rsp+2A0h+var_280], rax
0x14001863a  movdqu  xmmword ptr [rsp+2A0h+var_230], xmm0
0x140018640  call    ?StatItemAsCaller@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::StatItemAsCaller(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x140018645  mov     ebx, eax
0x140018647  test    rdi, rdi
0x14001864a  jz      short loc_140018654
0x14001864c  mov     rcx, rdi; this
0x14001864f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140018654  test    ebx, ebx
0x140018656  jns     short loc_140018684
0x140018658  lea     rax, aPushStatLayerI; "PUSH: Stat layer item"
0x14001865f  mov     r8, 2280002106Fh; struct UnionFs::StackEventTracer *
0x140018669  lea     r9, aUnionfsUnionfs_13; "UnionFs::UnionFsFilter::PreCreateFileOv"...
0x140018670  mov     [rsp+2A0h+var_280], rax; char *
0x140018675  mov     rdx, rsi; int
0x140018678  mov     ecx, ebx; this
0x14001867a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001867f  jmp     loc_140019479
0x140018684  mov     eax, 104h
0x140018689  cmp     ebx, eax
0x14001868b  jnz     short loc_140018694
0x14001868d  mov     ebx, eax
0x14001868f  jmp     loc_140019479
0x140018694  mov     rbx, [rbp+1A0h+var_1F0]
0x140018698  mov     eax, [rbp+1A0h+var_4C]
0x14001869e  mov     [rbp+1A0h+var_218], eax
0x1400186a1  mov     rcx, [rbx+48h]; Context
0x1400186a5  call    cs:__imp_FltReferenceContext
0x1400186ac  nop     dword ptr [rax+rax+00h]
0x1400186b1  mov     rax, [rbx+48h]
0x1400186b5  lea     rcx, [rbp+1A0h+Resource]
0x1400186b9  mov     [rsp+2A0h+Context], rax
0x1400186be  mov     rbx, [rax+20h]
0x1400186c2  mov     rdx, [rbx+78h]
0x1400186c6  add     rdx, 38h ; '8'
0x1400186ca  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x1400186cf  mov     rax, [r15+10h]
0x1400186d3  lea     r9, [rsp+2A0h+Context]
0x1400186d8  mov     [rsp+2A0h+var_260], rsi
0x1400186dd  mov     r8, r13
0x1400186e0  mov     [rsp+2A0h+var_268], r14
0x1400186e5  mov     rdx, r15
0x1400186e8  mov     [rbp+1A0h+var_21C], r12b
0x1400186ec  mov     rcx, [rax+18h]
0x1400186f0  mov     dword ptr [rsp+2A0h+var_230+4], 0Bh
0x1400186f8  mov     [rbp+1A0h+var_220], 0Ch
0x1400186ff  mov     [rsp+2A0h+var_250], r12b
0x140018704  mov     rax, [rcx+8]
0x140018708  mov     ecx, [rax+18h]
0x14001870b  xor     eax, eax
0x14001870d  mov     word ptr [rsp+2A0h+var_230+0Dh], ax
0x140018712  or      ecx, 2
0x140018715  mov     byte ptr [rsp+2A0h+var_230+0Fh], al
0x140018719  mov     [rbp+1A0h+var_21B], ax
0x14001871d  lea     edi, [rax+1]
0x140018720  mov     [rbp+1A0h+var_219], al
0x140018723  lea     rax, [rsp+2A0h+var_250]
0x140018728  mov     dword ptr [rsp+2A0h+var_230], ecx
0x14001872c  mov     [rsp+2A0h+var_270], rax
0x140018731  lea     rax, [rsp+2A0h+var_230]
0x140018736  mov     [rsp+2A0h+var_278], rbx; char *
0x14001873b  mov     [rsp+2A0h+var_280], rax
0x140018740  mov     dword ptr [rsp+2A0h+var_230+8], ecx
0x140018744  mov     byte ptr [rsp+2A0h+var_230+0Ch], dil
0x140018749  call    ?CheckOplockAndShareAccess@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@$$QEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBUCheckOplockAndShareAccessParams@12@AEAVUfsFsContext@2@PEA_NAEAUCreateContext@2@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::CheckOplockAndShareAccess(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &&,UnionFs::UnionFsFilter::CheckOplockAndShareAccessParams const &,UnionFs::UfsFsContext &,bool *,UnionFs::CreateContext &,UnionFs::StackEventTracer &)
0x14001874e  xor     r9d, r9d
0x140018751  mov     ebx, eax
0x140018753  test    eax, eax
0x140018755  jns     short loc_1400187BE
0x140018757  lea     rax, aPushOplockAndS; "PUSH: Oplock and share access check"
0x14001875e  mov     r8, 6EA0002109Fh; struct UnionFs::StackEventTracer *
0x140018768  lea     r9, aUnionfsUnionfs_13; "UnionFs::UnionFsFilter::PreCreateFileOv"...
0x14001876f  mov     [rsp+2A0h+var_280], rax; char *
0x140018774  mov     rdx, rsi; int
0x140018777  mov     ecx, ebx; this
0x140018779  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001877e  mov     rcx, [rbp+1A0h+Resource]; Resource
0x140018782  test    rcx, rcx
0x140018785  jz      short loc_14001879F
0x140018787  call    cs:__imp_ExReleaseResourceLite
0x14001878e  nop     dword ptr [rax+rax+00h]
0x140018793  call    cs:__imp_KeLeaveCriticalRegion
0x14001879a  nop     dword ptr [rax+rax+00h]
0x14001879f  mov     rcx, [rsp+2A0h+Context]; Context
0x1400187a4  test    rcx, rcx
0x1400187a7  jz      loc_140019479
0x1400187ad  call    cs:__imp_FltReleaseContext
0x1400187b4  nop     dword ptr [rax+rax+00h]
0x1400187b9  jmp     loc_140019479
0x1400187be  cmp     ebx, 103h
0x1400187c4  jnz     short loc_1400187D2
0x1400187c6  mov     rax, [rbp+1A0h+var_1B8]
0x1400187ca  mov     dword ptr [rax], 2
0x1400187d0  jmp     short loc_1400187D9
0x1400187d2  cmp     [rsp+2A0h+var_250], r9b
0x1400187d7  jz      short loc_14001881C
0x1400187d9  mov     rcx, [rbp+1A0h+Resource]; Resource
0x1400187dd  test    rcx, rcx
0x1400187e0  jz      short loc_1400187FD
0x1400187e2  call    cs:__imp_ExReleaseResourceLite
0x1400187e9  nop     dword ptr [rax+rax+00h]
0x1400187ee  call    cs:__imp_KeLeaveCriticalRegion
0x1400187f5  nop     dword ptr [rax+rax+00h]
0x1400187fa  xor     r9d, r9d
0x1400187fd  mov     rcx, [rsp+2A0h+Context]; Context
0x140018802  test    rcx, rcx
0x140018805  jz      loc_140019476
0x14001880b  call    cs:__imp_FltReleaseContext
0x140018812  nop     dword ptr [rax+rax+00h]
0x140018817  jmp     loc_140019473
0x14001881c  mov     rcx, [rbp+1A0h+Resource]; Resource
0x140018820  mov     r12b, dil
0x140018823  mov     [rsp+2A0h+var_250], dil
0x140018828  test    rcx, rcx
0x14001882b  jz      short loc_140018848
0x14001882d  call    cs:__imp_ExReleaseResourceLite
0x140018834  nop     dword ptr [rax+rax+00h]
0x140018839  call    cs:__imp_KeLeaveCriticalRegion
0x140018840  nop     dword ptr [rax+rax+00h]
0x140018845  xor     r9d, r9d
0x140018848  mov     rcx, [rsp+2A0h+Context]; Context
0x14001884d  test    rcx, rcx
0x140018850  jz      short loc_1400188A1
0x140018852  call    cs:__imp_FltReleaseContext
0x140018859  nop     dword ptr [rax+rax+00h]
0x14001885e  jmp     short loc_14001889E
0x140018860  mov     rcx, [rbp+1A0h+var_1E0]; Resource
0x140018864  mov     [rbp+1A0h+var_1E0], r9
0x140018868  test    rcx, rcx
0x14001886b  jz      short loc_140018888
0x14001886d  call    cs:__imp_ExReleaseResourceLite
0x140018874  nop     dword ptr [rax+rax+00h]
0x140018879  call    cs:__imp_KeLeaveCriticalRegion
0x140018880  nop     dword ptr [rax+rax+00h]
0x140018885  xor     r9d, r9d
0x140018888  mov     rcx, [rbp+1A0h+var_1F0+8]; this
0x14001888c  mov     [rbp+1A0h+var_1F0+8], r9
0x140018890  mov     [rbp+1A0h+var_1F0], r9
0x140018894  test    rcx, rcx
0x140018897  jz      short loc_1400188A1
0x140018899  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001889e  xor     r9d, r9d
0x1400188a1  cmp     dword ptr [rbp+1A0h+var_1D8], 2
0x1400188a5  mov     [rsp+2A0h+Context], r9
0x1400188aa  jnz     loc_140018964
0x1400188b0  mov     rax, qword ptr [rbp+1A0h+var_1D0+8]
0x1400188b4  lea     r8, [rsp+2A0h+var_230]; Source
0x1400188b9  mov     rcx, [r14]
0x1400188bc  lea     rdx, [rbp+1A0h+Resource]; struct _UNICODE_STRING *
0x1400188c0  add     rcx, 8; this
0x1400188c4  mov     [rsp+2A0h+var_278], rsi; char *
0x1400188c9  movzx   r9d, word ptr [rax+18h]
  ... truncated ...
```
