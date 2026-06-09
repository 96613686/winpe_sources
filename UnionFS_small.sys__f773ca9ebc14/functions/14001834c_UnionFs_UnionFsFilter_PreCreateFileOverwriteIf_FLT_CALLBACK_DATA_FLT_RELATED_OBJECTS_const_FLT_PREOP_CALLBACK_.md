# UnionFs::UnionFsFilter::PreCreateFileOverwriteIf(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x14001834c`
- end: `0x14001942f`
- name: `?PreCreateFileOverwriteIf@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `4323`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140011e00`

## callees

- `0x140002354`
- `0x14000c20c`
- `0x14000efd0`
- `0x14000f7fc`
- `0x140010b88`
- `0x140010de0`
- `0x140011198`
- `0x1400114c4`
- `0x14001834c`
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

- `ntoskrnl!ExFreePoolWithTag` at `0x1400188c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018945`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018abb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018bf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018db4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018de3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018e47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ffb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001912a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400193d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400188c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018945`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018abb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018b63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018bf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018c60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018d05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018db4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018de3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018e47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018f15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018ffb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001912a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400193d7`
- `ntoskrnl!PsGetHostSilo` at `0x140018560`
- `ntoskrnl!PsGetHostSilo` at `0x140018560`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018707`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018762`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400187ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400187ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019189`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018707`
- `ntoskrnl!ExReleaseResourceLite` at `0x140018762`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400187ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400187ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x140019189`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018713`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001876e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400187b9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400187f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019195`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018713`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001876e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400187b9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400187f9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140019195`
- `FLTMGR!FltReferenceContext` at `0x140018625`
- `FLTMGR!FltReferenceContext` at `0x140018625`
- `FLTMGR!FltReleaseContext` at `0x14001872d`
- `FLTMGR!FltReleaseContext` at `0x14001878b`
- `FLTMGR!FltReleaseContext` at `0x1400187d2`
- `FLTMGR!FltReleaseContext` at `0x14001872d`
- `FLTMGR!FltReleaseContext` at `0x14001878b`
- `FLTMGR!FltReleaseContext` at `0x1400187d2`

## string_xrefs

- `0x140018430`: `PUSH: Cache lookup`
- `0x1400184e4`: `results.CacheEntry->GetOriginalScratchPath()`
- `0x1400188fd`: `PUSH: Allocating scratch path for layer lookup`
- `0x14001849c`: `!FlagOn(Cbd.Iopb->Parameters.Create.Options, FILE_DIRECTORY_FILE)`
- `0x1400186d7`: `PUSH: Oplock and share access check`
- `0x140018d72`: `PUSH: Preparing for scratch create`
- `0x14001904b`: `!layer && !fullPathInLayer`
- `0x140018527`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x1400185e9`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x1400186e8`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x14001888c`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018a7f`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018b2a`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018bc8`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018d83`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018ed9`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018fbd`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x1400190d6`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140019205`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x1400192e9`: `UnionFs::UnionFsFilter::PreCreateFileOverwriteIf`
- `0x140018508`: `Failing overwrite_if on exact match for renamed tombstone`
- `0x140018514`: `ORIGIN: Attempt to overwrite_if a directory by opening it as a non-directory`

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
    v18 = 0x22700020FF2LL;
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
  if ( *((_WORD *)v118[0] + 80) == 4 )
  {
    if ( !*((_QWORD *)v118[0] + 26) )
      MicrosoftTelemetryAssertTriggeredMsgKM("results.CacheEntry->GetOriginalScratchPath()");
    if ( DWORD1(v117) == 1 )
    {
      if ( (a2->Iopb->Parameters.Create.Options & 0x40) == 0 )
        MicrosoftTelemetryAssertTriggeredMsgKM("Failing overwrite_if on exact match for renamed tombstone");
      v15 = -1073741638;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC00000BALL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x38900021041LL,
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
      v38 = 0x384000210BDLL;
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
        v38 = 0x397000210C8LL;
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
    UnicodeString.Buffer = (PWSTR)off_14007E740;
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
          (struct UnionFs::StackEventTracer *)0xFA000210F1LL,
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
        (struct UnionFs::StackEventTracer *)0x40200021100LL,
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
        (struct UnionFs::StackEventTracer *)0xFB0002110BLL,
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
            (struct UnionFs::StackEventTracer *)0x7C00021137LL,
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
                (struct UnionFs::StackEventTracer *)0x78800021163LL,
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
                (unsigned int)byte_140095F6D,
                v77,
                (unsigned int)v123,
                (__int64)v110);
            }
            UnionFs::ProcessTraceStatusOrigin(
              (UnionFs *)0xC0000022LL,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x78900021175LL,
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
              (struct UnionFs::StackEventTracer *)0x42000021198LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
              "PUSH: ConvertToSoftTombstone for COW",
              (const char *)v102);
            wil::details::lambda_call__lambda_63c2f4f8ba5a9901913a9c2784aa4f1c___::_lambda_call__lambda_63c2f4f8ba5a9901913a9c2784aa4f1c___(v110);
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
              (struct UnionFs::StackEventTracer *)0x294000211ADLL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
              "PUSH: Preparing for COW",
              (const char *)v104);
            wil::details::lambda_call__lambda_63c2f4f8ba5a9901913a9c2784aa4f1c___::_lambda_call__lambda_63c2f4f8ba5a9901913a9c2784aa4f1c___(v110);
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
            (struct UnionFs::StackEventTracer *)0x293000211BFLL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOverwriteIf",
            "PUSH: Performing COW",
            (const char *)v105);
          if ( !v131 )
            UnicodeString = 0;
          FsFltWil::Details::FreeUnicodeString(&UnicodeString, v98);
          if ( v127[0] )
            utl::_RefCountBase::_DecStrong(v127[0]);
          wil::details::lambda_call__lambda_63c2f4f8ba5a9901913a9c2784aa4f1c___::_lambda_call__lambda_63c2f4f8ba5a9901913a9c2784aa4f1c___(v110);
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
        wil::details::lambda_call__lambda_63c2f4f8ba5a9901913a9c2784aa4f1c___::_lambda_call__lambda_63c2f4f8ba5a9901913a9c2784aa4f1c___(v110);
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
    v18 = 0x2280002105BLL;
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
    (struct UnionFs::StackEventTracer *)0x6EA0002108BLL,
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
0x14001834c  mov     [rsp-8+arg_0], rbx
0x140018351  push    rbp
0x140018352  push    rsi
0x140018353  push    rdi
0x140018354  push    r12
0x140018356  push    r13
0x140018358  push    r14
0x14001835a  push    r15
0x14001835c  lea     rbp, [rsp-170h]
0x140018364  sub     rsp, 270h
0x14001836b  mov     rax, cs:__security_cookie
0x140018372  xor     rax, rsp
0x140018375  mov     [rbp+1A0h+var_40], rax
0x14001837c  mov     rax, [rbp+1A0h+arg_30]
0x140018383  mov     rdi, r9
0x140018386  mov     r14, [rbp+1A0h+arg_20]
0x14001838d  xor     ecx, ecx
0x14001838f  mov     rsi, [rbp+1A0h+arg_28]
0x140018396  xorps   xmm1, xmm1
0x140018399  mov     [r9], ecx
0x14001839c  xorps   xmm0, xmm0
0x14001839f  mov     [rbp+1A0h+var_1B8], r9
0x1400183a3  mov     r13, r8
0x1400183a6  mov     [rbp+1A0h+var_1A8], rax
0x1400183aa  mov     r15, rdx
0x1400183ad  mov     rax, [r8+20h]
0x1400183b1  mov     [rbp+1A0h+var_1C0], r8
0x1400183b5  mov     r9d, [rax+50h]
0x1400183b9  shr     r9d, 11h
0x1400183bd  movd    eax, xmm1
0x1400183c1  not     r9d
0x1400183c4  movdqa  [rbp+1A0h+var_200], xmm1
0x1400183c9  and     r9d, 1
0x1400183cd  or      r9d, 8
0x1400183d1  movdqa  xmmword ptr [rbp+1A0h+var_1F0], xmm0
0x1400183d6  or      eax, 3
0x1400183d9  mov     [rbp+1A0h+var_1E0], rcx
0x1400183dd  mov     dword ptr [rbp+1A0h+var_200], eax
0x1400183e0  mov     rax, [r14+8]
0x1400183e4  mov     [rbp+1A0h+var_1D8], rcx
0x1400183e8  movdqa  [rbp+1A0h+var_1D0], xmm0
0x1400183ed  cmp     dword ptr [rax+1Ch], 2
0x1400183f1  jnz     short loc_1400183FD
0x1400183f3  mov     rax, [rax+20h]
0x1400183f7  mov     rcx, [rax+10h]
0x1400183fb  jmp     short loc_140018408
0x1400183fd  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140018404  mov     rcx, [rax+50h]
0x140018408  mov     r8, [r14]
0x14001840b  lea     rax, [rbp+1A0h+var_200]
0x14001840f  mov     rdx, [r13+18h]
0x140018413  mov     [rsp+2A0h+var_270], r15
0x140018418  mov     [rsp+2A0h+var_278], rsi; char *
0x14001841d  mov     [rsp+2A0h+var_280], rax
0x140018422  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140018427  xor     r9d, r9d
0x14001842a  mov     ebx, eax
0x14001842c  test    eax, eax
0x14001842e  jns     short loc_140018446
0x140018430  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x140018437  mov     r8, 22700020FF2h
0x140018441  jmp     loc_1400185E9
0x140018446  mov     eax, dword ptr [rbp+1A0h+var_200+4]
0x140018449  mov     r12b, r9b
0x14001844c  mov     [rbp+1A0h+var_218], r9d
0x140018450  mov     edx, 4
0x140018455  mov     [rsp+2A0h+var_250], r9b
0x14001845a  test    eax, eax
0x14001845c  jz      loc_140018821
0x140018462  test    byte ptr [rbp+1A0h+var_200+8], dl
0x140018465  jz      short loc_1400184AD
0x140018467  lea     ebx, [rdx-3]
0x14001846a  cmp     eax, ebx
0x14001846c  jz      short loc_140018481
0x14001846e  mov     dword ptr [r15+18h], 0C000003Ah
0x140018476  mov     [r15+20h], r9
0x14001847a  mov     [rdi], edx
0x14001847c  jmp     loc_1400193F6
0x140018481  lea     rdx, [rbp+1A0h+var_1F0]
0x140018485  mov     rcx, r14
0x140018488  call    ?OverwriteTombstone@CreateContext@UnionFs@@QEAAX$$QEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@Z; UnionFs::CreateContext::OverwriteTombstone(utl::shared_ptr<UnionFs::UfsPathCachePayload> &&)
0x14001848d  mov     rax, [r15+10h]
0x140018491  mov     ecx, [rax+20h]
0x140018494  test    bl, cl
0x140018496  jz      loc_1400193F3
0x14001849c  lea     rcx, aFlagonCbdIopbP; "!FlagOn(Cbd.Iopb->Parameters.Create.Opt"...
0x1400184a3  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400184a8  jmp     loc_1400193F3
0x1400184ad  mov     edi, 1
0x1400184b2  cmp     dword ptr [rbp+1A0h+var_1D8], edi
0x1400184b5  jnz     short loc_1400184C6
0x1400184b7  mov     rax, [r14+0A0h]
0x1400184be  or      dword ptr [rax], 8
0x1400184c1  jmp     loc_1400193F6
0x1400184c6  mov     rax, [rbp+1A0h+var_1F0]
0x1400184ca  movzx   ecx, word ptr [rax+0A0h]
0x1400184d1  nop
0x1400184d2  cmp     cx, dx
0x1400184d5  jnz     short loc_140018545
0x1400184d7  mov     rax, [rbp+1A0h+var_1F0]
0x1400184db  cmp     [rax+0D0h], r9
0x1400184e2  jnz     short loc_1400184F3
0x1400184e4  lea     rcx, aResultsCacheen; "results.CacheEntry->GetOriginalScratchP"...
0x1400184eb  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400184f0  xor     r9d, r9d
0x1400184f3  cmp     dword ptr [rbp+1A0h+var_200+4], edi
0x1400184f6  jnz     loc_1400187E0
0x1400184fc  mov     rax, [r15+10h]
0x140018500  mov     ecx, [rax+20h]
0x140018503  test    cl, 40h
0x140018506  jnz     short loc_140018514
0x140018508  lea     rcx, aFailingOverwri_0; "Failing overwrite_if on exact match for"...
0x14001850f  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140018514  lea     rax, aOriginAttemptT_0; "ORIGIN: Attempt to overwrite_if a direc"...
0x14001851b  mov     ebx, 0C00000BAh
0x140018520  mov     ecx, ebx; this
0x140018522  mov     [rsp+2A0h+var_280], rax; char *
0x140018527  lea     r9, aUnionfsUnionfs_13; "UnionFs::UnionFsFilter::PreCreateFileOv"...
0x14001852e  mov     r8, 38900021041h; struct UnionFs::StackEventTracer *
0x140018538  mov     rdx, rsi; int
0x14001853b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140018540  jmp     loc_1400193F9
0x140018545  cmp     dword ptr [rbp+1A0h+var_200+4], edi
0x140018548  jnz     loc_1400187E0
0x14001854e  xor     edx, edx; Val
0x140018550  lea     rcx, [rbp+1A0h+var_90]; void *
0x140018557  lea     r8d, [rdx+48h]; Size
0x14001855b  call    memset
0x140018560  call    cs:__imp_PsGetHostSilo
0x140018567  nop     dword ptr [rax+rax+00h]
0x14001856c  mov     r8, rax
0x14001856f  xor     r12d, r12d
0x140018572  mov     rax, [rbp+1A0h+var_1F0]
0x140018576  mov     rdi, [rax+28h]
0x14001857a  mov     rcx, [rax+20h]
0x14001857e  test    rdi, rdi
0x140018581  jz      short loc_14001858B
0x140018583  lock inc dword ptr [rdi+8]
0x140018587  mov     rax, [rbp+1A0h+var_1F0]
0x14001858b  mov     rax, [rax+30h]
0x14001858f  mov     r9d, 4
0x140018595  mov     rcx, [rcx+8]
0x140018599  mov     [rsp+2A0h+var_270], rsi
0x14001859e  mov     [rsp+2A0h+var_278], r15; char *
0x1400185a3  movups  xmm0, xmmword ptr [rax]
0x1400185a6  mov     rdx, [rcx]
0x1400185a9  lea     rax, [rbp+1A0h+var_90]
0x1400185b0  lea     rcx, [rsp+2A0h+var_230]
0x1400185b5  mov     [rsp+2A0h+var_280], rax
0x1400185ba  movdqu  xmmword ptr [rsp+2A0h+var_230], xmm0
0x1400185c0  call    ?StatItemAsCaller@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::StatItemAsCaller(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x1400185c5  mov     ebx, eax
0x1400185c7  test    rdi, rdi
0x1400185ca  jz      short loc_1400185D4
0x1400185cc  mov     rcx, rdi; this
0x1400185cf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400185d4  test    ebx, ebx
0x1400185d6  jns     short loc_140018604
0x1400185d8  lea     rax, aPushStatLayerI; "PUSH: Stat layer item"
0x1400185df  mov     r8, 2280002105Bh; struct UnionFs::StackEventTracer *
0x1400185e9  lea     r9, aUnionfsUnionfs_13; "UnionFs::UnionFsFilter::PreCreateFileOv"...
0x1400185f0  mov     [rsp+2A0h+var_280], rax; char *
0x1400185f5  mov     rdx, rsi; int
0x1400185f8  mov     ecx, ebx; this
0x1400185fa  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400185ff  jmp     loc_1400193F9
0x140018604  mov     eax, 104h
0x140018609  cmp     ebx, eax
0x14001860b  jnz     short loc_140018614
0x14001860d  mov     ebx, eax
0x14001860f  jmp     loc_1400193F9
0x140018614  mov     rbx, [rbp+1A0h+var_1F0]
0x140018618  mov     eax, [rbp+1A0h+var_4C]
0x14001861e  mov     [rbp+1A0h+var_218], eax
0x140018621  mov     rcx, [rbx+48h]; Context
0x140018625  call    cs:__imp_FltReferenceContext
0x14001862c  nop     dword ptr [rax+rax+00h]
0x140018631  mov     rax, [rbx+48h]
0x140018635  lea     rcx, [rbp+1A0h+Resource]
0x140018639  mov     [rsp+2A0h+Context], rax
0x14001863e  mov     rbx, [rax+20h]
0x140018642  mov     rdx, [rbx+78h]
0x140018646  add     rdx, 38h ; '8'
0x14001864a  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x14001864f  mov     rax, [r15+10h]
0x140018653  lea     r9, [rsp+2A0h+Context]
0x140018658  mov     [rsp+2A0h+var_260], rsi
0x14001865d  mov     r8, r13
0x140018660  mov     [rsp+2A0h+var_268], r14
0x140018665  mov     rdx, r15
0x140018668  mov     [rbp+1A0h+var_21C], r12b
0x14001866c  mov     rcx, [rax+18h]
0x140018670  mov     dword ptr [rsp+2A0h+var_230+4], 0Bh
0x140018678  mov     [rbp+1A0h+var_220], 0Ch
0x14001867f  mov     [rsp+2A0h+var_250], r12b
0x140018684  mov     rax, [rcx+8]
0x140018688  mov     ecx, [rax+18h]
0x14001868b  xor     eax, eax
0x14001868d  mov     word ptr [rsp+2A0h+var_230+0Dh], ax
0x140018692  or      ecx, 2
0x140018695  mov     byte ptr [rsp+2A0h+var_230+0Fh], al
0x140018699  mov     [rbp+1A0h+var_21B], ax
0x14001869d  lea     edi, [rax+1]
0x1400186a0  mov     [rbp+1A0h+var_219], al
0x1400186a3  lea     rax, [rsp+2A0h+var_250]
0x1400186a8  mov     dword ptr [rsp+2A0h+var_230], ecx
0x1400186ac  mov     [rsp+2A0h+var_270], rax
0x1400186b1  lea     rax, [rsp+2A0h+var_230]
0x1400186b6  mov     [rsp+2A0h+var_278], rbx; char *
0x1400186bb  mov     [rsp+2A0h+var_280], rax
0x1400186c0  mov     dword ptr [rsp+2A0h+var_230+8], ecx
0x1400186c4  mov     byte ptr [rsp+2A0h+var_230+0Ch], dil
0x1400186c9  call    ?CheckOplockAndShareAccess@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@$$QEAV?$unique_ptr@VUfsStreamCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBUCheckOplockAndShareAccessParams@12@AEAVUfsFsContext@2@PEA_NAEAUCreateContext@2@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::CheckOplockAndShareAccess(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,wistd::unique_ptr<UnionFs::UfsStreamCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &&,UnionFs::UnionFsFilter::CheckOplockAndShareAccessParams const &,UnionFs::UfsFsContext &,bool *,UnionFs::CreateContext &,UnionFs::StackEventTracer &)
0x1400186ce  xor     r9d, r9d
0x1400186d1  mov     ebx, eax
0x1400186d3  test    eax, eax
0x1400186d5  jns     short loc_14001873E
0x1400186d7  lea     rax, aPushOplockAndS; "PUSH: Oplock and share access check"
0x1400186de  mov     r8, 6EA0002108Bh; struct UnionFs::StackEventTracer *
0x1400186e8  lea     r9, aUnionfsUnionfs_13; "UnionFs::UnionFsFilter::PreCreateFileOv"...
0x1400186ef  mov     [rsp+2A0h+var_280], rax; char *
0x1400186f4  mov     rdx, rsi; int
0x1400186f7  mov     ecx, ebx; this
0x1400186f9  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400186fe  mov     rcx, [rbp+1A0h+Resource]; Resource
0x140018702  test    rcx, rcx
0x140018705  jz      short loc_14001871F
0x140018707  call    cs:__imp_ExReleaseResourceLite
0x14001870e  nop     dword ptr [rax+rax+00h]
0x140018713  call    cs:__imp_KeLeaveCriticalRegion
0x14001871a  nop     dword ptr [rax+rax+00h]
0x14001871f  mov     rcx, [rsp+2A0h+Context]; Context
0x140018724  test    rcx, rcx
0x140018727  jz      loc_1400193F9
0x14001872d  call    cs:__imp_FltReleaseContext
0x140018734  nop     dword ptr [rax+rax+00h]
0x140018739  jmp     loc_1400193F9
0x14001873e  cmp     ebx, 103h
0x140018744  jnz     short loc_140018752
0x140018746  mov     rax, [rbp+1A0h+var_1B8]
0x14001874a  mov     dword ptr [rax], 2
0x140018750  jmp     short loc_140018759
0x140018752  cmp     [rsp+2A0h+var_250], r9b
0x140018757  jz      short loc_14001879C
0x140018759  mov     rcx, [rbp+1A0h+Resource]; Resource
0x14001875d  test    rcx, rcx
0x140018760  jz      short loc_14001877D
0x140018762  call    cs:__imp_ExReleaseResourceLite
0x140018769  nop     dword ptr [rax+rax+00h]
0x14001876e  call    cs:__imp_KeLeaveCriticalRegion
0x140018775  nop     dword ptr [rax+rax+00h]
0x14001877a  xor     r9d, r9d
0x14001877d  mov     rcx, [rsp+2A0h+Context]; Context
0x140018782  test    rcx, rcx
0x140018785  jz      loc_1400193F6
0x14001878b  call    cs:__imp_FltReleaseContext
0x140018792  nop     dword ptr [rax+rax+00h]
0x140018797  jmp     loc_1400193F3
0x14001879c  mov     rcx, [rbp+1A0h+Resource]; Resource
0x1400187a0  mov     r12b, dil
0x1400187a3  mov     [rsp+2A0h+var_250], dil
0x1400187a8  test    rcx, rcx
0x1400187ab  jz      short loc_1400187C8
0x1400187ad  call    cs:__imp_ExReleaseResourceLite
0x1400187b4  nop     dword ptr [rax+rax+00h]
0x1400187b9  call    cs:__imp_KeLeaveCriticalRegion
0x1400187c0  nop     dword ptr [rax+rax+00h]
0x1400187c5  xor     r9d, r9d
0x1400187c8  mov     rcx, [rsp+2A0h+Context]; Context
0x1400187cd  test    rcx, rcx
0x1400187d0  jz      short loc_140018821
0x1400187d2  call    cs:__imp_FltReleaseContext
0x1400187d9  nop     dword ptr [rax+rax+00h]
0x1400187de  jmp     short loc_14001881E
0x1400187e0  mov     rcx, [rbp+1A0h+var_1E0]; Resource
0x1400187e4  mov     [rbp+1A0h+var_1E0], r9
0x1400187e8  test    rcx, rcx
0x1400187eb  jz      short loc_140018808
0x1400187ed  call    cs:__imp_ExReleaseResourceLite
0x1400187f4  nop     dword ptr [rax+rax+00h]
0x1400187f9  call    cs:__imp_KeLeaveCriticalRegion
0x140018800  nop     dword ptr [rax+rax+00h]
0x140018805  xor     r9d, r9d
0x140018808  mov     rcx, [rbp+1A0h+var_1F0+8]; this
0x14001880c  mov     [rbp+1A0h+var_1F0+8], r9
0x140018810  mov     [rbp+1A0h+var_1F0], r9
0x140018814  test    rcx, rcx
0x140018817  jz      short loc_140018821
0x140018819  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001881e  xor     r9d, r9d
0x140018821  cmp     dword ptr [rbp+1A0h+var_1D8], 2
0x140018825  mov     [rsp+2A0h+Context], r9
0x14001882a  jnz     loc_1400188E4
0x140018830  mov     rax, qword ptr [rbp+1A0h+var_1D0+8]
0x140018834  lea     r8, [rsp+2A0h+var_230]; Source
0x140018839  mov     rcx, [r14]
0x14001883c  lea     rdx, [rbp+1A0h+Resource]; struct _UNICODE_STRING *
0x140018840  add     rcx, 8; this
0x140018844  mov     [rsp+2A0h+var_278], rsi; char *
0x140018849  movzx   r9d, word ptr [rax+18h]
  ... truncated ...
```
