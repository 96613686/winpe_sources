# UnionFs::UnionFsFilter::QueryOpen(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::UfsStreamHandleCtx &,UnionFs::UfsUnionCtx const &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x14001a10c`
- end: `0x14001ab00`
- name: `?QueryOpen@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAU_FLT_FILE_NAME_INFORMATION@@AEAVUfsStreamHandleCtx@2@AEBVUfsUnionCtx@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `2548`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, struct _FLT_FILE_NAME_INFORMATION *, struct UnionFs::UfsStreamHandleCtx *, const struct UnionFs::UfsUnionCtx *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `25`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140011e00`

## callees

- `0x1400015c4`
- `0x14000227c`
- `0x14000efd0`
- `0x14000f7fc`
- `0x140010b88`
- `0x140011198`
- `0x14001a10c`
- `0x140024034`
- `0x14003cd88`
- `0x14004397c`
- `0x140043ef4`
- `0x1400569d4`
- `0x140056a14`
- `0x140056ac4`
- `0x140056afc`
- `0x140061090`
- `0x14006f7fc`
- `0x140077f14`
- `0x140079a24`
- `0x140079c48`
- `0x140079da0`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001a61f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a69e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a7f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a852`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001aaac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a61f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a69e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a7f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a852`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001aaac`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14001a2d5`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14001a2d5`
- `FLTMGR!FltAcknowledgeEcp` at `0x14001aa84`
- `FLTMGR!FltAcknowledgeEcp` at `0x14001aa84`

## string_xrefs

- `0x14001a198`: `ORIGIN: Unsupported IRP_MJ_QUERY_OPEN info class`
- `0x14001a1a4`: `UnionFs::UnionFsFilter::QueryOpen`
- `0x14001a273`: `UnionFs::UnionFsFilter::QueryOpen`
- `0x14001a3ec`: `UnionFs::UnionFsFilter::QueryOpen`
- `0x14001a4c2`: `UnionFs::UnionFsFilter::QueryOpen`
- `0x14001a4fb`: `UnionFs::UnionFsFilter::QueryOpen`
- `0x14001a5eb`: `UnionFs::UnionFsFilter::QueryOpen`
- `0x14001a6d1`: `UnionFs::UnionFsFilter::QueryOpen`
- `0x14001a762`: `UnionFs::UnionFsFilter::QueryOpen`
- `0x14001a260`: `ORIGIN: Unsupported QoC ECP classes for query open`
- `0x14001a4b1`: `PUSH: Cache lookup`
- `0x14001a56e`: `results.CacheEntry->GetOriginalScratchPath()`
- `0x14001a658`: `PUSH: Allocating scratch path for layer lookup`
- `0x14001a7bb`: `ORIGIN: Path not found`
- `0x14001a868`: `ORIGIN: Tombstone replaced or renamed`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::QueryOpen(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_IO_PARAMETER_BLOCK *a3,
        struct _FLT_FILE_NAME_INFORMATION *a4,
        struct _FLT_TAG_DATA_BUFFER *a5,
        const struct UnionFs::UfsUnionCtx *a6,
        struct UnionFs::StackEventTracer *a7,
        const struct UnionFs::UfsSiloCtx *a8)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  bool v11; // zf
  unsigned int v12; // ebx
  int v13; // r8d
  int v14; // r9d
  PFLT_IO_PARAMETER_BLOCK v15; // rax
  ULONG EaLength; // ecx
  bool QueryOnCreateEcp; // al
  _DWORD *v18; // r14
  PFILE_OBJECT EaList; // rbx
  unsigned int v20; // edi
  ULONG_PTR Information; // rbx
  PFLT_INSTANCE SecurityContext; // rdx
  int v23; // r15d
  __int16 v24; // ax
  unsigned __int16 v25; // ax
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // r12d
  int v29; // r9d
  __int64 v30; // r9
  __int64 v31; // rcx
  int v32; // r8d
  int v33; // r9d
  struct _FLT_IO_PARAMETER_BLOCK *v34; // rax
  char v36; // di
  int v37; // eax
  struct _UNICODE_STRING *v38; // rdx
  const char *v39; // rcx
  __int64 v40; // r8
  struct _UNICODE_STRING *v41; // rdx
  ULONG_PTR v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rbx
  unsigned __int64 v45; // r9
  const struct UnionFs::UfsUnionCtx *Pointer; // rdi
  int v47; // eax
  unsigned __int64 v48; // r9
  utl::_RefCountBase *v49; // rcx
  char v50; // al
  utl::_RefCountBase *v51; // rcx
  utl::_RefCountBase *v52; // rcx
  __int128 v53; // xmm6
  __int128 v54; // xmm7
  union _LARGE_INTEGER v55; // xmm8_8
  __int128 v56; // xmm0
  PFLT_IO_PARAMETER_BLOCK v57; // rax
  unsigned int v58; // edx
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  UCHAR MajorFunction; // cl
  unsigned __int64 *v62; // rdx
  __int64 v63; // rax
  volatile signed __int32 *v64; // rdi
  const struct UnionFs::UfsLayerCtx *v65; // rsi
  union _LARGE_INTEGER *v66; // rax
  utl::_RefCountBase *v67; // rcx
  char *v68; // [rsp+30h] [rbp-D8h]
  char *v69; // [rsp+30h] [rbp-D8h]
  char v70; // [rsp+48h] [rbp-C0h]
  _WORD v71[3]; // [rsp+4Ah] [rbp-BEh] BYREF
  UnionFs::Rtl *v72; // [rsp+50h] [rbp-B8h] BYREF
  struct _FLT_CALLBACK_DATA P; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v74; // [rsp+B0h] [rbp-58h]
  __int128 v75; // [rsp+B8h] [rbp-50h]
  struct _UNICODE_STRING v76; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v77; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v78; // [rsp+F8h] [rbp-10h]
  __int128 v79; // [rsp+108h] [rbp+0h]
  __int128 v80; // [rsp+118h] [rbp+10h]
  char *v81; // [rsp+158h] [rbp+50h]
  UNICODE_STRING Source; // [rsp+168h] [rbp+60h] BYREF
  union _LARGE_INTEGER v83[10]; // [rsp+178h] [rbp+70h] BYREF

  P.TagData = a5;
  Iopb = a2->Iopb;
  P.IoStatus.Information = (ULONG_PTR)a4;
  P.Iopb = a3;
  v11 = Iopb->MajorFunction == 0xF9;
  P.IoStatus.Pointer = a6;
  if ( v11 && Iopb->Parameters.Create.EaLength != 68 )
  {
    v12 = -1073741637;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC00000BBLL,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x2EE0002039BLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::QueryOpen",
      "ORIGIN: Unsupported IRP_MJ_QUERY_OPEN info class",
      v68);
    if ( (unsigned int)dword_14009E178 > 2 )
    {
      v15 = a2->Iopb;
      P.Iopb = (const PFLT_IO_PARAMETER_BLOCK)"UnionFs::UnionFsFilter::QueryOpen";
      EaLength = v15->Parameters.Create.EaLength;
      v71[0] = 923;
      LODWORD(P.Thread) = EaLength;
      LODWORD(v72) = 750;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        EaLength,
        (unsigned int)byte_1400962E5,
        v13,
        v14,
        (__int64)&P.Iopb,
        (__int64)&v72,
        (__int64)v71,
        (__int64)&P.Thread);
    }
    return v12;
  }
  *(_QWORD *)&P.Flags = 0;
  LODWORD(P.Thread) = 0;
  QueryOnCreateEcp = UnionFs::Utils::GetQueryOnCreateEcp(
                       a2,
                       &P,
                       (struct _QUERY_ON_CREATE_ECP_CONTEXT **)&P.Thread,
                       (unsigned int *)a6);
  v18 = *(_DWORD **)&P.Flags;
  if ( QueryOnCreateEcp && (**(_DWORD **)&P.Flags & 0xFFFFFFFE) != 0 )
  {
    v12 = -1073741637;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC00000BBLL,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x7CA000203A8LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::QueryOpen",
      "ORIGIN: Unsupported QoC ECP classes for query open",
      v68);
    return v12;
  }
  *((_QWORD *)&v77 + 1) = off_14007E740;
  v81 = (char *)&v77 + 8;
  UnionFs::StackEventTracer::SetIgnoreStatusCallback(a7, &v77);
  EaList = (PFILE_OBJECT)a3->Parameters.QueryEa.EaList;
  v20 = ((EaList->Flags & 0x20000) == 0) | 2;
  memset(v83, 0, 0x48u);
  IoGetTransactionParameterBlock(EaList);
  Information = P.IoStatus.Information;
  SecurityContext = (PFLT_INSTANCE)a3->Parameters.Create.SecurityContext;
  v72 = (UnionFs::Rtl *)(P.IoStatus.Information + 8);
  v23 = UnionFs::Utils::StatItem(P.IoStatus.Information + 8, SecurityContext, v20, v83, a7);
  v24 = *((_WORD *)a7 + 245);
  if ( v24 )
  {
    v25 = v24 - 1;
    *((_WORD *)a7 + 245) = v25;
    v26 = 120 * (v25 + 1LL);
    v27 = *(_QWORD *)((char *)a7 + v26);
    *(_QWORD *)((char *)a7 + v26) = 0;
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
  }
  v28 = -1073741772;
  if ( v23 >= 0 )
  {
    v70 = 1;
LABEL_13:
    v29 = ~(*((_DWORD *)P.Iopb->Parameters.QueryEa.EaList + 20) >> 17);
    memset(&P.QueueLinks, 0, 40);
    v30 = v29 & 1;
    LODWORD(P.QueueLinks.Flink) = _mm_cvtsi128_si32((__m128i)0LL) | 3;
    v74 = 0;
    v75 = 0;
    if ( *((_DWORD *)P.IoStatus.Pointer + 7) == 2 )
      v31 = *(_QWORD *)(*((_QWORD *)P.IoStatus.Pointer + 4) + 16LL);
    else
      v31 = *((_QWORD *)UnionFs::g_FilterState + 10);
    v69 = (char *)a7;
    v12 = UnionFs::UfsPathCache::LookupEntry(v31, P.Iopb->Parameters.WMI.ProviderId, Information, v30, &P.QueueLinks);
    if ( (v12 & 0x80000000) != 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)v12,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x466000203ECLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::QueryOpen",
        "PUSH: Cache lookup",
        (const char *)a7);
LABEL_107:
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&P.QueueLinks);
      return v12;
    }
    v36 = 1;
    if ( HIDWORD(P.FilterContext[0]) )
    {
      if ( ((__int64)P.FilterContext[1] & 4) != 0 )
      {
        if ( HIDWORD(P.FilterContext[0]) != 1 )
          v28 = -1073741766;
        UnionFs::ProcessTraceInfoOrigin(
          (UnionFs *)v28,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x5F700020402LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::QueryOpen",
          "ORIGIN: Hard tombstone",
          (const char *)v72,
          (const struct _UNICODE_STRING *)a2);
LABEL_30:
        v12 = v28;
        goto LABEL_107;
      }
      if ( (_DWORD)v74 == 1 )
      {
        v36 = 0;
        *(_QWORD *)&P.Flags = 0;
        goto LABEL_48;
      }
      if ( *((_WORD *)P.QueueContext[0] + 80) == 4 )
      {
        if ( !*((_QWORD *)P.QueueContext[0] + 26) )
          MicrosoftTelemetryAssertTriggeredMsgKM("results.CacheEntry->GetOriginalScratchPath()");
        if ( HIDWORD(P.FilterContext[0]) == 1 )
          v36 = 0;
      }
    }
    *(_QWORD *)&P.Flags = 0;
    if ( (_DWORD)v74 == 2 )
    {
      Source = (UNICODE_STRING)**((_OWORD **)&v75 + 1);
      v76 = *(struct _UNICODE_STRING *)v75;
      v37 = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(v72, &v76, &Source, &P, (int)a7);
      LODWORD(v72) = v37;
      if ( v37 < 0 )
      {
        v39 = "PUSH: Replacing substring";
        v40 = 0x4680002042BLL;
LABEL_41:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v37,
          (int)a7,
          (struct UnionFs::StackEventTracer *)v40,
          (unsigned __int64)"UnionFs::UnionFsFilter::QueryOpen",
          v39,
          v69);
        v42 = *(_QWORD *)&P.Flags;
        if ( !*(_QWORD *)&P.Flags )
        {
LABEL_46:
          v12 = (unsigned int)v72;
          goto LABEL_107;
        }
        if ( !*(_BYTE *)(*(_QWORD *)&P.Flags + 16LL) )
          *(_OWORD *)*(_QWORD *)&P.Flags = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v42, v41);
LABEL_45:
        ExFreePoolWithTag((PVOID)v42, 0);
        goto LABEL_46;
      }
      v43 = *(_QWORD *)&P.Flags;
      if ( *(_QWORD *)&P.Flags )
      {
LABEL_51:
        v44 = *(_QWORD *)&P.TagData[2].SymbolicLinkReparseBuffer.SubstituteNameOffset;
        *(_QWORD *)&P.TagData[2].SymbolicLinkReparseBuffer.SubstituteNameOffset = v43;
        if ( v44 )
        {
          if ( !*(_BYTE *)(v44 + 16) )
            *(_OWORD *)v44 = 0;
          FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v44, v38);
          ExFreePoolWithTag((PVOID)v44, 0);
        }
        utl::make_unique<UnionFs::FindAndStatResults,,0>(&P.IoStatus.Information);
        v42 = P.IoStatus.Information;
        if ( !P.IoStatus.Information )
        {
          v12 = -1073741670;
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC000009ALL,
            (int)a7,
            (struct UnionFs::StackEventTracer *)0x3F900020440LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::QueryOpen",
            "ORIGIN: Allocating findAndStatResults",
            v69);
          goto LABEL_107;
        }
        LOBYTE(v71[0]) = 0;
        if ( v36 )
        {
          Pointer = (const struct UnionFs::UfsUnionCtx *)P.IoStatus.Pointer;
          v76 = *(struct _UNICODE_STRING *)*(_QWORD *)&P.TagData[2].SymbolicLinkReparseBuffer.SubstituteNameOffset;
          v47 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(
                  P.IoStatus.Pointer,
                  &v76,
                  P.TagData,
                  (*((_DWORD *)P.Iopb->Parameters.QueryEa.EaList + 20) & 0x20000) == 0,
                  P.IoStatus.Information);
          LODWORD(v72) = v47;
          if ( v47 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v47,
              (int)a7,
              (struct UnionFs::StackEventTracer *)0x1F20002044ELL,
              (unsigned __int64)"UnionFs::UnionFsFilter::QueryOpen",
              "PUSH: Probing for item in layers",
              (const char *)a7);
            if ( !v42 )
              goto LABEL_46;
            v49 = *(utl::_RefCountBase **)(v42 + 88);
            if ( v49 )
              utl::_RefCountBase::_DecStrong(v49);
            goto LABEL_45;
          }
          if ( *(_WORD *)v42 != 1 )
          {
            if ( *(_WORD *)v42 == 2 && v23 == -1073741766 )
            {
              UnionFs::ProcessTraceInfoOrigin(
                (UnionFs *)0xC000003ALL,
                (int)a7,
                (struct UnionFs::StackEventTracer *)0x5F000020457LL,
                v48,
                "ORIGIN: Path not found",
                (const char *)a7);
              if ( v42 )
              {
                v51 = *(utl::_RefCountBase **)(v42 + 88);
                if ( v51 )
                  utl::_RefCountBase::_DecStrong(v51);
                ExFreePoolWithTag((PVOID)v42, 0);
              }
              v12 = -1073741766;
              goto LABEL_107;
            }
            v23 = 0;
            if ( !v70 )
            {
              UnionFs::ProcessTraceInfoOrigin(
                (UnionFs *)0xC0000034LL,
                (int)a7,
                (struct UnionFs::StackEventTracer *)0x5F10002045BLL,
                v48,
                "ORIGIN: Name not found",
                (const char *)a7);
              if ( v42 )
              {
                v52 = *(utl::_RefCountBase **)(v42 + 88);
                if ( v52 )
                  utl::_RefCountBase::_DecStrong(v52);
                ExFreePoolWithTag((PVOID)v42, 0);
              }
              goto LABEL_30;
            }
            v50 = 0;
            goto LABEL_85;
          }
          v50 = 1;
        }
        else
        {
          if ( v23 < 0 )
          {
            UnionFs::ProcessTraceInfoOrigin(
              (UnionFs *)(unsigned int)v23,
              (int)a7,
              (struct UnionFs::StackEventTracer *)0x5F200020462LL,
              v45,
              "ORIGIN: Tombstone replaced or renamed",
              v69);
LABEL_102:
            if ( v42 )
            {
              v67 = *(utl::_RefCountBase **)(v42 + 88);
              if ( v67 )
                utl::_RefCountBase::_DecStrong(v67);
              ExFreePoolWithTag((PVOID)v42, 0);
            }
            v12 = v23;
            goto LABEL_107;
          }
          Pointer = (const struct UnionFs::UfsUnionCtx *)P.IoStatus.Pointer;
          v50 = v71[0];
        }
        v23 = 0;
        if ( !v70 )
        {
          v53 = *(_OWORD *)(v42 + 24);
          v54 = *(_OWORD *)(v42 + 40);
          v55 = *(union _LARGE_INTEGER *)(v42 + 72);
          v77 = *(_OWORD *)(v42 + 8);
          v56 = *(_OWORD *)(v42 + 56);
          v78 = v53;
          v80 = v56;
          v79 = v54;
          goto LABEL_81;
        }
LABEL_85:
        v53 = *(_OWORD *)&v83[2].LowPart;
        v54 = *(_OWORD *)&v83[4].LowPart;
        v55 = v83[8];
        v77 = *(_OWORD *)&v83[0].LowPart;
        v80 = *(_OWORD *)&v83[6].LowPart;
        v78 = *(_OWORD *)&v83[2].LowPart;
        v79 = *(_OWORD *)&v83[4].LowPart;
        if ( !v50 || v83[1].QuadPart != *(_QWORD *)(v42 + 16) )
        {
          FsFltWil::AcquirePushLockShared(&P.Iopb, (char *)Pointer + 72);
          v63 = *((_QWORD *)Pointer + 6);
          v64 = *(volatile signed __int32 **)(v63 + 8);
          v65 = *(const struct UnionFs::UfsLayerCtx **)v63;
          if ( v64 )
            _InterlockedIncrement(v64 + 2);
          if ( P.Iopb )
            FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)P.Iopb, v62);
          *(_QWORD *)&v77 = *(_QWORD *)UnionFs::UfsFileID::UfsFileID(
                                         (UnionFs::UfsFileID *)&v76,
                                         v83[0],
                                         v65,
                                         (const struct UnionFs::UfsUnionCtx *)P.IoStatus.Pointer);
          if ( v64 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v64);
          goto LABEL_82;
        }
LABEL_81:
        *(_QWORD *)&v77 = *(_QWORD *)UnionFs::UfsFileID::UfsFileID(
                                       (UnionFs::UfsFileID *)&v76,
                                       *(union _LARGE_INTEGER *)(v42 + 8),
                                       *(const struct UnionFs::UfsLayerCtx **)(v42 + 80),
                                       Pointer);
LABEL_82:
        v57 = a2->Iopb;
        v58 = DWORD2(v80) & 0xFF7FFFFF;
        v59 = v77;
        DWORD2(v80) &= ~0x800000u;
        v60 = v80;
        MajorFunction = v57->MajorFunction;
        if ( MajorFunction == 0xF2 )
        {
          *((_QWORD *)v57->Parameters.QueryEa.EaList + 4) = *((_QWORD *)&v79 + 1);
          *((_QWORD *)a2->Iopb->Parameters.QueryEa.EaList + 3) = v79;
          *a2->Iopb->Parameters.AcquireForModifiedPageWriter.ResourceToRelease = (PERESOURCE)*((_QWORD *)&v77 + 1);
          *((_QWORD *)a2->Iopb->Parameters.QueryEa.EaList + 5) = v80;
          *((_DWORD *)a2->Iopb->Parameters.QueryEa.EaList + 12) = v58;
          *(_OWORD *)((char *)a2->Iopb->Parameters.QueryEa.EaList + 8) = v78;
        }
        else if ( MajorFunction == 0xF9 )
        {
          v66 = (union _LARGE_INTEGER *)v57->Parameters.QueryEa.EaList;
          *(_OWORD *)&v66->LowPart = v77;
          *(_OWORD *)&v66[2].LowPart = v53;
          *(_OWORD *)&v66[4].LowPart = v54;
          *(_OWORD *)&v66[6].LowPart = v60;
          v66[8] = v55;
        }
        if ( v18 && (*v18 & 1) != 0 )
        {
          v18[1] |= 1u;
          if ( LODWORD(P.Thread) >= 0x58 )
          {
            *((_OWORD *)v18 + 1) = v59;
            *((_OWORD *)v18 + 2) = v53;
            *((_OWORD *)v18 + 3) = v54;
            *((_OWORD *)v18 + 4) = v60;
            *((union _LARGE_INTEGER *)v18 + 10) = v55;
          }
          else
          {
            v18[2] |= 1u;
          }
          FltAcknowledgeEcp(*(PFLT_FILTER *)UnionFs::g_FilterState, v18);
        }
        a2->IoStatus.Status = 0;
        goto LABEL_102;
      }
    }
LABEL_48:
    v37 = UnionFs::UfsPathName::AllocAndInit(P.IoStatus.Information, &P, a7);
    LODWORD(v72) = v37;
    if ( v37 < 0 )
    {
      v39 = "PUSH: Allocating scratch path for layer lookup";
      v40 = 0x46900020436LL;
      goto LABEL_41;
    }
    v43 = *(_QWORD *)&P.Flags;
    goto LABEL_51;
  }
  v70 = 0;
  if ( v23 == -1073741766 || v23 == -1073741772 )
    goto LABEL_13;
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v23,
    (int)a7,
    (struct UnionFs::StackEventTracer *)0x1F1000203D5LL,
    (unsigned __int64)"UnionFs::UnionFsFilter::QueryOpen",
    "PUSH: Querying stat information",
    (const char *)a8);
  if ( (unsigned int)dword_14009E178 > 4 )
  {
    v11 = *(_QWORD *)(Information + 16) == 0;
    v34 = (struct _FLT_IO_PARAMETER_BLOCK *)&FsTlEmptyUnicodeString;
    LODWORD(v72) = 497;
    if ( !v11 )
      v34 = (struct _FLT_IO_PARAMETER_BLOCK *)(Information + 8);
    P.TagData = (struct _FLT_TAG_DATA_BUFFER *)"UnionFs::UnionFsFilter::QueryOpen";
    P.Iopb = v34;
    v71[0] = 981;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapBuffer<_UNICODE_STRING>>(
      Information + 8,
      (unsigned int)&dword_1400964CC,
      v32,
      v33,
      (__int64)&P.TagData,
      (__int64)&v72,
      (__int64)v71,
      (__int64)&P.Iopb);
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x14001a10c  mov     rax, rsp
0x14001a10f  mov     [rax+8], rbx
0x14001a113  push    rbp
0x14001a114  push    rsi
0x14001a115  push    rdi
0x14001a116  push    r12
0x14001a118  push    r13
0x14001a11a  push    r14
0x14001a11c  push    r15
0x14001a11e  lea     rbp, [rax-138h]
0x14001a125  sub     rsp, 200h
0x14001a12c  movaps  xmmword ptr [rax-48h], xmm6
0x14001a130  movaps  xmmword ptr [rax-58h], xmm7
0x14001a134  movaps  xmmword ptr [rax-68h], xmm8
0x14001a139  mov     rax, cs:__security_cookie
0x14001a140  xor     rax, rsp
0x14001a143  mov     [rbp+130h+var_70], rax
0x14001a14a  mov     rax, [rbp+130h+arg_20]
0x14001a151  mov     r12, r8
0x14001a154  mov     rsi, [rbp+130h+arg_30]
0x14001a15b  mov     r13, rdx
0x14001a15e  mov     r15, [rbp+130h+arg_38]
0x14001a165  mov     [rsp+230h+var_1B8], rax
0x14001a16a  mov     rax, [rdx+10h]
0x14001a16e  mov     [rsp+230h+var_1C0], r9
0x14001a173  mov     r9, [rbp+130h+arg_28]; unsigned int *
0x14001a17a  mov     [rsp+230h+var_1D0], r8
0x14001a17f  cmp     byte ptr [rax+4], 0F9h
0x14001a183  mov     [rsp+230h+var_1C8], r9
0x14001a188  jnz     loc_14001A231
0x14001a18e  cmp     dword ptr [rax+30h], 44h ; 'D'
0x14001a192  jz      loc_14001A231
0x14001a198  lea     rax, aOriginUnsuppor; "ORIGIN: Unsupported IRP_MJ_QUERY_OPEN i"...
0x14001a19f  mov     ebx, 0C00000BBh
0x14001a1a4  lea     rdi, aUnionfsUnionfs_65; "UnionFs::UnionFsFilter::QueryOpen"
0x14001a1ab  mov     [rsp+230h+var_210], rax; char *
0x14001a1b0  mov     r9, rdi; unsigned __int64
0x14001a1b3  mov     ecx, ebx; this
0x14001a1b5  mov     r8, 2EE0002039Bh; struct UnionFs::StackEventTracer *
0x14001a1bf  mov     rdx, rsi; int
0x14001a1c2  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001a1c7  mov     eax, cs:dword_14009E178
0x14001a1cd  cmp     eax, 2
0x14001a1d0  jbe     loc_14001AAC4
0x14001a1d6  mov     rax, [r13+10h]
0x14001a1da  lea     rdx, byte_1400962E5
0x14001a1e1  mov     [rsp+230h+var_1D0], rdi
0x14001a1e6  mov     ecx, [rax+30h]
0x14001a1e9  mov     eax, 39Bh
0x14001a1ee  mov     word ptr [rsp+230h+var_1F0+2], ax
0x14001a1f3  lea     rax, [rsp+230h+var_1D8]
0x14001a1f8  mov     qword ptr [rsp+230h+var_1F8], rax
0x14001a1fd  lea     rax, [rsp+230h+var_1F0+2]
0x14001a202  mov     [rsp+230h+var_200], rax
0x14001a207  lea     rax, [rsp+230h+var_1E8]
0x14001a20c  mov     [rsp+230h+var_208], rax
0x14001a211  lea     rax, [rsp+230h+var_1D0]
0x14001a216  mov     [rsp+230h+var_210], rax
0x14001a21b  mov     dword ptr [rsp+230h+var_1D8], ecx
0x14001a21f  mov     dword ptr [rsp+230h+var_1E8], 2EEh
0x14001a227  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x14001a22c  jmp     loc_14001AAC4
0x14001a231  xor     ebx, ebx
0x14001a233  lea     r8, [rsp+230h+var_1D8]; struct _QUERY_ON_CREATE_ECP_CONTEXT **
0x14001a238  lea     rdx, [rsp+230h+P]; struct _FLT_CALLBACK_DATA *
0x14001a23d  mov     [rsp+230h+P], rbx
0x14001a242  mov     rcx, r13; CallbackData
0x14001a245  mov     dword ptr [rsp+230h+var_1D8], ebx
0x14001a249  call    ?GetQueryOnCreateEcp@Utils@UnionFs@@YA_NAEBU_FLT_CALLBACK_DATA@@PEAPEAU_QUERY_ON_CREATE_ECP_CONTEXT@@PEAK@Z; UnionFs::Utils::GetQueryOnCreateEcp(_FLT_CALLBACK_DATA const &,_QUERY_ON_CREATE_ECP_CONTEXT * *,ulong *)
0x14001a24e  mov     r14, [rsp+230h+P]
0x14001a253  test    al, al
0x14001a255  jz      short loc_14001A291
0x14001a257  test    dword ptr [r14], 0FFFFFFFEh
0x14001a25e  jz      short loc_14001A291
0x14001a260  lea     rax, aOriginUnsuppor_0; "ORIGIN: Unsupported QoC ECP classes for"...
0x14001a267  mov     ebx, 0C00000BBh
0x14001a26c  mov     ecx, ebx; this
0x14001a26e  mov     [rsp+230h+var_210], rax; char *
0x14001a273  lea     r9, aUnionfsUnionfs_65; "UnionFs::UnionFsFilter::QueryOpen"
0x14001a27a  mov     r8, 7CA000203A8h; struct UnionFs::StackEventTracer *
0x14001a284  mov     rdx, rsi; int
0x14001a287  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001a28c  jmp     loc_14001AAC4
0x14001a291  lea     rax, off_14007E740
0x14001a298  mov     rcx, rsi
0x14001a29b  mov     qword ptr [rbp+130h+var_150+8], rax
0x14001a29f  lea     rdx, [rbp+130h+var_150]
0x14001a2a3  lea     rax, [rbp+130h+var_150+8]
0x14001a2a7  mov     [rbp+130h+var_E0], rax
0x14001a2ab  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x14001a2b0  mov     rbx, [r12+20h]
0x14001a2b5  lea     rcx, [rbp+130h+var_C0]; void *
0x14001a2b9  xor     edx, edx; Val
0x14001a2bb  mov     edi, [rbx+50h]
0x14001a2be  shr     edi, 11h
0x14001a2c1  lea     r8d, [rdx+48h]; Size
0x14001a2c5  not     edi
0x14001a2c7  and     edi, 1
0x14001a2ca  or      edi, 2
0x14001a2cd  call    memset
0x14001a2d2  mov     rcx, rbx; FileObject
0x14001a2d5  call    cs:__imp_IoGetTransactionParameterBlock
0x14001a2dc  nop     dword ptr [rax+rax+00h]
0x14001a2e1  mov     rbx, [rsp+230h+var_1C0]
0x14001a2e6  lea     r9, [rbp+130h+var_C0]
0x14001a2ea  mov     rdx, [r12+18h]
0x14001a2ef  mov     r8d, edi
0x14001a2f2  mov     qword ptr [rsp+230h+var_1F8], r13
0x14001a2f7  mov     [rsp+230h+var_200], rax
0x14001a2fc  lea     rcx, [rbx+8]
0x14001a300  mov     [rsp+230h+var_208], r15; char *
0x14001a305  mov     [rsp+230h+var_1E8], rcx
0x14001a30a  mov     [rsp+230h+var_210], rsi
0x14001a30f  call    ?StatItem@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@QEAU_TXN_PARAMETER_BLOCK@@PEAU_FLT_CALLBACK_DATA@@@Z; UnionFs::Utils::StatItem(_UNICODE_STRING const &,_FLT_INSTANCE const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *,_TXN_PARAMETER_BLOCK * const,_FLT_CALLBACK_DATA *)
0x14001a314  xor     edi, edi
0x14001a316  mov     r15d, eax
0x14001a319  movzx   eax, word ptr [rsi+1EAh]
0x14001a320  lea     r8d, [rdi+1]
0x14001a324  test    ax, ax
0x14001a327  jz      short loc_14001A35E
0x14001a329  sub     ax, r8w
0x14001a32d  movzx   ecx, ax
0x14001a330  mov     [rsi+1EAh], cx
0x14001a337  add     rcx, r8
0x14001a33a  imul    rcx, 78h ; 'x'
0x14001a33e  mov     rdx, [rcx+rsi]
0x14001a342  mov     [rcx+rsi], rdi
0x14001a346  test    rdx, rdx
0x14001a349  jz      short loc_14001A35E
0x14001a34b  mov     rax, [rdx]
0x14001a34e  mov     rcx, rdx
0x14001a351  mov     rax, [rax+18h]
0x14001a355  call    _guard_dispatch_icall
0x14001a35a  lea     r8d, [rdi+1]
0x14001a35e  mov     r12d, 0C0000034h
0x14001a364  test    r15d, r15d
0x14001a367  js      short loc_14001A3C8
0x14001a369  mov     byte ptr [rsp+230h+var_1F0], r8b
0x14001a36e  mov     rdx, [rsp+230h+var_1D0]
0x14001a373  xorps   xmm1, xmm1
0x14001a376  xorps   xmm0, xmm0
0x14001a379  mov     rax, [rdx+20h]
0x14001a37d  mov     r9d, [rax+50h]
0x14001a381  shr     r9d, 11h
0x14001a385  movd    eax, xmm1
0x14001a389  not     r9d
0x14001a38c  movdqa  [rbp+130h+var_1B0], xmm1
0x14001a391  and     r9d, r8d
0x14001a394  movdqa  [rbp+130h+var_1A0], xmm0
0x14001a399  or      eax, 3
0x14001a39c  mov     [rbp+130h+var_190], rdi
0x14001a3a0  mov     dword ptr [rbp+130h+var_1B0], eax
0x14001a3a3  mov     rax, [rsp+230h+var_1C8]
0x14001a3a8  mov     [rbp+130h+var_188], rdi
0x14001a3ac  movdqa  [rbp+130h+var_180], xmm0
0x14001a3b1  cmp     dword ptr [rax+1Ch], 2
0x14001a3b5  jnz     loc_14001A481
0x14001a3bb  mov     rax, [rax+20h]
0x14001a3bf  mov     rcx, [rax+10h]
0x14001a3c3  jmp     loc_14001A48C
0x14001a3c8  mov     byte ptr [rsp+230h+var_1F0], dil
0x14001a3cd  cmp     r15d, 0C000003Ah
0x14001a3d4  jz      short loc_14001A36E
0x14001a3d6  cmp     r15d, r12d
0x14001a3d9  jz      short loc_14001A36E
0x14001a3db  lea     rax, aPushQueryingSt; "PUSH: Querying stat information"
0x14001a3e2  mov     r8, 1F1000203D5h; struct UnionFs::StackEventTracer *
0x14001a3ec  lea     rdi, aUnionfsUnionfs_65; "UnionFs::UnionFsFilter::QueryOpen"
0x14001a3f3  mov     [rsp+230h+var_210], rax; char *
0x14001a3f8  mov     r9, rdi; unsigned __int64
0x14001a3fb  mov     rdx, rsi; int
0x14001a3fe  mov     ecx, r15d; this
0x14001a401  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001a406  mov     eax, cs:dword_14009E178
0x14001a40c  mov     edx, 4
0x14001a411  cmp     eax, edx
0x14001a413  jbe     short loc_14001A479
0x14001a415  cmp     qword ptr [rbx+10h], 0
0x14001a41a  lea     rcx, [rbx+8]
0x14001a41e  lea     rax, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x14001a425  mov     dword ptr [rsp+230h+var_1E8], 1F1h
0x14001a42d  cmovnz  rax, rcx
0x14001a431  mov     [rsp+230h+var_1B8], rdi
0x14001a436  mov     [rsp+230h+var_1D0], rax
0x14001a43b  lea     rdx, dword_1400964CC
0x14001a442  mov     eax, 3D5h
0x14001a447  mov     word ptr [rsp+230h+var_1F0+2], ax
0x14001a44c  lea     rax, [rsp+230h+var_1D0]
0x14001a451  mov     qword ptr [rsp+230h+var_1F8], rax
0x14001a456  lea     rax, [rsp+230h+var_1F0+2]
0x14001a45b  mov     [rsp+230h+var_200], rax
0x14001a460  lea     rax, [rsp+230h+var_1E8]
0x14001a465  mov     [rsp+230h+var_208], rax
0x14001a46a  lea     rax, [rsp+230h+var_1B8]
0x14001a46f  mov     [rsp+230h+var_210], rax
0x14001a474  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x14001a479  mov     eax, r15d
0x14001a47c  jmp     loc_14001AAC6
0x14001a481  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001a488  mov     rcx, [rax+50h]
0x14001a48c  mov     rdx, [rdx+18h]
0x14001a490  lea     rax, [rbp+130h+var_1B0]
0x14001a494  mov     [rsp+230h+var_200], r13; struct _UNICODE_STRING *
0x14001a499  mov     r8, rbx
0x14001a49c  mov     [rsp+230h+var_208], rsi; char *
0x14001a4a1  mov     [rsp+230h+var_210], rax
0x14001a4a6  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x14001a4ab  mov     ebx, eax
0x14001a4ad  test    eax, eax
0x14001a4af  jns     short loc_14001A4DD
0x14001a4b1  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x14001a4b8  mov     r8, 466000203ECh; struct UnionFs::StackEventTracer *
0x14001a4c2  lea     r9, aUnionfsUnionfs_65; "UnionFs::UnionFsFilter::QueryOpen"
0x14001a4c9  mov     [rsp+230h+var_210], rax; char *
0x14001a4ce  mov     rdx, rsi; int
0x14001a4d1  mov     ecx, ebx; this
0x14001a4d3  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001a4d8  jmp     loc_14001AABB
0x14001a4dd  mov     eax, dword ptr [rbp+130h+var_1B0+4]
0x14001a4e0  xor     ebx, ebx
0x14001a4e2  mov     ecx, 1
0x14001a4e7  mov     edi, ecx
0x14001a4e9  test    eax, eax
0x14001a4eb  jz      loc_14001A580
0x14001a4f1  lea     edx, [rcx+3]
0x14001a4f4  test    byte ptr [rbp+130h+var_1B0+8], dl
0x14001a4f7  jz      short loc_14001A53E
0x14001a4f9  cmp     eax, ecx
0x14001a4fb  lea     r9, aUnionfsUnionfs_65; "UnionFs::UnionFsFilter::QueryOpen"
0x14001a502  mov     rcx, [rsp+230h+var_1E8]
0x14001a507  lea     rax, aOriginHardTomb; "ORIGIN: Hard tombstone"
0x14001a50e  mov     [rsp+230h+var_208], rcx; char *
0x14001a513  mov     ebx, 0C000003Ah
0x14001a518  cmovnz  r12d, ebx
0x14001a51c  mov     [rsp+230h+var_210], rax; char *
0x14001a521  mov     ecx, r12d; this
0x14001a524  mov     r8, 5F700020402h; struct UnionFs::StackEventTracer *
0x14001a52e  mov     rdx, rsi; int
0x14001a531  call    ?ProcessTraceInfoOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceInfoOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x14001a536  mov     ebx, r12d
0x14001a539  jmp     loc_14001AABB
0x14001a53e  cmp     dword ptr [rbp+130h+var_188], ecx
0x14001a541  jnz     short loc_14001A550
0x14001a543  mov     dil, bl
0x14001a546  mov     [rsp+230h+P], rbx
0x14001a54b  jmp     loc_14001A63E
0x14001a550  mov     rax, qword ptr [rbp+130h+var_1A0]
0x14001a554  movzx   ecx, word ptr [rax+0A0h]
0x14001a55b  nop
0x14001a55c  cmp     cx, dx
0x14001a55f  jnz     short loc_14001A580
0x14001a561  mov     rax, qword ptr [rbp+130h+var_1A0]
0x14001a565  cmp     [rax+0D0h], rbx
0x14001a56c  jnz     short loc_14001A57A
0x14001a56e  lea     rcx, aResultsCacheen; "results.CacheEntry->GetOriginalScratchP"...
0x14001a575  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001a57a  cmp     dword ptr [rbp+130h+var_1B0+4], edi
0x14001a57d  cmovz   edi, ebx
0x14001a580  cmp     dword ptr [rbp+130h+var_188], 2
0x14001a584  mov     [rsp+230h+P], rbx
0x14001a589  jnz     loc_14001A63E
0x14001a58f  mov     rax, qword ptr [rbp+130h+var_180+8]
0x14001a593  lea     r8, [rbp+130h+Source]; Source
0x14001a597  mov     rcx, [rsp+230h+var_1E8]; this
0x14001a59c  lea     rdx, [rbp+130h+var_170]; struct _UNICODE_STRING *
0x14001a5a0  mov     [rsp+230h+var_208], rsi; char *
0x14001a5a5  movzx   r9d, word ptr [rax+18h]
0x14001a5aa  movups  xmm0, xmmword ptr [rax]
0x14001a5ad  mov     rax, qword ptr [rbp+130h+var_180]
0x14001a5b1  movdqu  xmmword ptr [rbp+130h+Source.Length], xmm0
0x14001a5b6  movups  xmm1, xmmword ptr [rax]
0x14001a5b9  lea     rax, [rsp+230h+P]
0x14001a5be  mov     [rsp+230h+var_210], rax; P
0x14001a5c3  movdqu  xmmword ptr [rbp+130h+var_170.Length], xmm1
0x14001a5c8  call    ?AllocAndInitWithReplacedPathPrefix@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@00GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14001a5cd  mov     dword ptr [rsp+230h+var_1E8], eax
0x14001a5d1  test    eax, eax
0x14001a5d3  jns     short loc_14001A634
0x14001a5d5  lea     rcx, aPushReplacingS_3; "PUSH: Replacing substring"
0x14001a5dc  mov     r8, 4680002042Bh; struct UnionFs::StackEventTracer *
0x14001a5e6  mov     [rsp+230h+var_210], rcx; char *
0x14001a5eb  lea     r9, aUnionfsUnionfs_65; "UnionFs::UnionFsFilter::QueryOpen"
0x14001a5f2  mov     ecx, eax; this
0x14001a5f4  mov     rdx, rsi; int
0x14001a5f7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001a5fc  mov     rbx, [rsp+230h+P]
0x14001a601  test    rbx, rbx
0x14001a604  jz      short loc_14001A62B
0x14001a606  cmp     byte ptr [rbx+10h], 0
0x14001a60a  jnz     short loc_14001A612
0x14001a60c  xorps   xmm0, xmm0
0x14001a60f  movups  xmmword ptr [rbx], xmm0
0x14001a612  mov     rcx, rbx; UnicodeString
0x14001a615  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14001a61a  xor     edx, edx; Tag
0x14001a61c  mov     rcx, rbx; P
0x14001a61f  call    cs:__imp_ExFreePoolWithTag
0x14001a626  nop     dword ptr [rax+rax+00h]
0x14001a62b  mov     ebx, dword ptr [rsp+230h+var_1E8]
0x14001a62f  jmp     loc_14001AABB
  ... truncated ...
```
