# UnionFs::PostRename(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,void *,UnionFs::StackEventTracer &)

- ea: `0x14002c9f0`
- end: `0x14002d336`
- name: `?PostRename@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@PEAXAEAVStackEventTracer@1@@Z`
- size: `2374`
- prototype: `int(UnionFs *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002d340`

## callees

- `0x140002878`
- `0x14000f7fc`
- `0x140010b88`
- `0x140023b7c`
- `0x14002bbcc`
- `0x14002bea4`
- `0x14002c9f0`
- `0x140036128`
- `0x1400421a0`
- `0x1400424ec`
- `0x1400429b0`
- `0x140042dd4`
- `0x1400430fc`
- `0x140043474`
- `0x140044748`
- `0x14004dd90`
- `0x140056ac4`
- `0x140056afc`
- `0x140061024`
- `0x140079c48`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002cdc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ce6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d055`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d0df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d12f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cdc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ce6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d055`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d0df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d12f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002cc59`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002ce04`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002cf7b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d205`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d30c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002cc59`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002ce04`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002cf7b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d205`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d30c`
- `ntoskrnl!KeSetEvent` at `0x14002ccec`
- `ntoskrnl!KeSetEvent` at `0x14002cd23`
- `ntoskrnl!KeSetEvent` at `0x14002ccec`
- `ntoskrnl!KeSetEvent` at `0x14002cd23`

## string_xrefs

- `0x14002cebf`: `PUSH: Failed to replace tombstone`
- `0x14002d092`: `PUSH: Failed to replace tombstone`
- `0x14002ca38`: `UnionFs::PostRename`
- `0x14002d23f`: `UnionFs::PostRename`
- `0x14002d2af`: `UnionFs::PostRename`
- `0x14002cad8`: `Renamed layer-backed file`
- `0x14002cb68`: `renameCtx->DestCacheEntry && renameCtx->DestCacheEntry->GetTombstoneState() == TombstoneState::Soft`
- `0x14002cbfd`: `PUSH: Renaming entry in path cache`
- `0x14002cd7a`: `PUSH: Copying original scratch path`
- `0x14002ce33`: `PUSH: Marking renamed`
- `0x14002cf03`: `PUSH: Marking renamed`
- `0x14002d18f`: `renameCtx->SourceScratchLayer`
- `0x14002d267`: `renameCtx->DestCacheEntry->GetTombstoneState() == TombstoneState::Soft`
- `0x14002cbe6`: `UnionFs::UfsPathCache::RenameDirectoryEntry`

## pseudocode

```c
__int64 __fastcall UnionFs::PostRename(
        UnionFs *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        struct UnionFs::StackEventTracer *a4)
{
  UnionFs::UfsPathCachePayload *v4; // rax
  const struct _UNICODE_STRING *v7; // rax
  struct _UNICODE_STRING *v8; // rax
  __int64 v9; // rcx
  char v10; // dl
  __int64 v11; // rax
  _QWORD *v12; // r8
  volatile signed __int32 *v13; // rbx
  __int64 v14; // r15
  __int64 v15; // rcx
  int v16; // r12d
  const char *v17; // rax
  __int64 v18; // r8
  PVOID v19; // rbx
  UnionFs::UfsEaTable *v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // rcx
  __int64 *v26; // rcx
  int v27; // r14d
  const char *v28; // rax
  __int64 v29; // r8
  struct _UNICODE_STRING *v30; // rdx
  struct _UNICODE_STRING *v31; // rdi
  PVOID v32; // rbx
  struct _UNICODE_STRING *v33; // rdx
  struct _UNICODE_STRING *v34; // r14
  __int64 v35; // rax
  const char *v36; // rax
  __int64 v37; // r8
  _QWORD *v38; // rbx
  PVOID v39; // rbx
  PVOID v40; // rcx
  volatile signed __int32 *v41; // r15
  __int64 v42; // r12
  UnionFs::UfsLayerCtx *v43; // rcx
  _BOOL8 v44; // r9
  utl::_RefCountBase *v45; // rcx
  UnionFs::UfsPathCachePayload *v46; // r12
  UnionFs::UfsPathCachePayload *v47; // rcx
  utl::_RefCountBase *v48; // rcx
  utl::_RefCountBase *v49; // rcx
  UnionFs::UfsPathCachePayload *v50; // rbx
  int v51; // ebx
  const char *v52; // rax
  __int64 v53; // r8
  PVOID v54; // rdi
  __int64 v55; // rax
  UnionFs::UfsPathCachePayload *v56; // rbx
  PVOID v57; // rbx
  char *v58; // [rsp+28h] [rbp-61h]
  const struct _UNICODE_STRING *v59; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING *v60; // [rsp+58h] [rbp-31h] BYREF
  const char *v61; // [rsp+60h] [rbp-29h] BYREF
  char v62[8]; // [rsp+68h] [rbp-21h] BYREF
  const char *v63; // [rsp+70h] [rbp-19h] BYREF
  PVOID *p_Entry; // [rsp+78h] [rbp-11h] BYREF
  char v65; // [rsp+80h] [rbp-9h]
  __int128 v66; // [rsp+88h] [rbp-1h] BYREF
  struct _UNICODE_STRING v67; // [rsp+98h] [rbp+Fh] BYREF
  PVOID P; // [rsp+F0h] [rbp+67h] BYREF
  PVOID Entry; // [rsp+100h] [rbp+77h] BYREF

  Entry = a3;
  p_Entry = &Entry;
  v4 = *(UnionFs::UfsPathCachePayload **)&a3->Size;
  v65 = 1;
  if ( *((_DWORD *)this + 6) )
  {
    if ( v4 )
    {
      v51 = UnionFs::UfsPathCachePayload::RevertSoftTombstone(v4, a4);
      if ( v51 < 0 )
      {
        v52 = "PUSH: reverting tombstone";
        v53 = 0x33B000B0488LL;
        goto LABEL_106;
      }
    }
    v55 = *((_QWORD *)Entry + 2);
    if ( v55 )
    {
      if ( *(_WORD *)(v55 + 160) != 1 )
        MicrosoftTelemetryAssertTriggeredMsgKM("renameCtx->DestCacheEntry->GetTombstoneState() == TombstoneState::Soft");
      if ( *(_WORD *)(*((_QWORD *)Entry + 2) + 162LL) )
      {
        v51 = UnionFs::UfsPathCachePayload::RevertSoftTombstone(*((UnionFs::UfsPathCachePayload **)Entry + 2), a4);
        if ( v51 < 0 )
        {
          v52 = "PUSH: reverting tombstone";
          v53 = 0x3D9000B0496LL;
          goto LABEL_106;
        }
      }
      else
      {
        v56 = (UnionFs::UfsPathCachePayload *)*((_QWORD *)Entry + 2);
        UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(v56, 0x44E000B049CLL);
        UnionFs::UfsPathCachePayload::RevertSoftTombstone(v56);
      }
    }
    goto LABEL_119;
  }
  if ( v4 )
  {
    v67 = *(struct _UNICODE_STRING *)&a3->FileObject->Type;
    v66 = *(_OWORD *)a3->Transaction;
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x20) != 0
      && (qword_14009E190 & 0x20) == qword_14009E190 )
    {
      v7 = (const struct _UNICODE_STRING *)&v66;
      LODWORD(P) = 982;
      if ( !*((_QWORD *)&v66 + 1) )
        v7 = &FsTlEmptyUnicodeString;
      *(_QWORD *)v62 = "UnionFs::PostRename";
      v59 = v7;
      v8 = &v67;
      if ( !v67.Buffer )
        v8 = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
      v60 = v8;
      v61 = "onecore\\base\\fs\\unionfs\\sys\\info.cpp";
      v63 = "Renamed layer-backed file";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>>(
        (unsigned int)&FsTlEmptyUnicodeString,
        (unsigned int)&byte_140096BEF,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&v63,
        (__int64)v62,
        (__int64)&v61,
        (__int64)&P,
        (__int64)&v60,
        (__int64)&v59);
    }
  }
  v9 = *((_QWORD *)Entry + 8);
  if ( !v9 )
  {
    if ( !*((_QWORD *)Entry + 6) )
      MicrosoftTelemetryAssertTriggeredMsgKM("Neither source nor destination exist in a union.");
    goto LABEL_101;
  }
  v10 = *((_BYTE *)Entry + 384);
  if ( (v10 & 2) == 0 )
  {
    v50 = (UnionFs::UfsPathCachePayload *)*((_QWORD *)Entry + 2);
    if ( v50 )
    {
      UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(*((_QWORD *)Entry + 2), 0x44B000B0469LL);
      UnionFs::UfsPathCachePayload::RevertSoftTombstone(v50);
    }
    goto LABEL_101;
  }
  if ( *((_QWORD *)Entry + 6) == v9 && (v10 & 1) != 0 )
  {
    v11 = *((_QWORD *)Entry + 2);
    if ( !v11 || *(_WORD *)(v11 + 160) != 1 )
      MicrosoftTelemetryAssertTriggeredMsgKM("renameCtx->DestCacheEntry && renameCtx->DestCacheEntry->GetTombstoneState() == TombstoneState::Soft");
    v12 = Entry;
    v13 = (volatile signed __int32 *)*((_QWORD *)Entry + 30);
    v14 = *((_QWORD *)Entry + 29);
    if ( v13 )
    {
      _InterlockedIncrement(v13 + 2);
      v12 = Entry;
    }
    if ( *(_DWORD *)(v14 + 28) == 2 )
      v15 = *(_QWORD *)(*(_QWORD *)(v14 + 32) + 16LL);
    else
      v15 = *((_QWORD *)UnionFs::g_FilterState + 10);
    LODWORD(v58) = 0;
    v16 = UnionFs::UfsPathTable::MoveSubtree(v15, a2->IoStatus.Pointer, v12[4], v12[5], a4);
    if ( v16 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v16,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x3C10010017ALL,
        (unsigned __int64)"UnionFs::UfsPathCache::RenameDirectoryEntry",
        "PUSH: Moving subtree",
        v58);
      v17 = "PUSH: Renaming entry in path cache";
      v18 = 0x3C5000B03F4LL;
      goto LABEL_25;
    }
    if ( *(_DWORD *)(v14 + 28) == 2 )
      v21 = *(UnionFs::UfsEaTable **)(*(_QWORD *)(v14 + 32) + 24LL);
    else
      v21 = (UnionFs::UfsEaTable *)*((_QWORD *)UnionFs::g_FilterState + 11);
    v16 = UnionFs::UfsEaTable::RenameDirectoryEntry(
            v21,
            (const struct _FLT_INSTANCE *)a2->IoStatus.Pointer,
            *((const struct UnionFs::UfsPathName **)Entry + 4),
            *((const struct UnionFs::UfsPathName **)Entry + 5),
            a4);
    if ( v16 < 0 )
    {
      v17 = "PUSH: Renaming entry in EA table";
      v18 = 0x689000B03FDLL;
LABEL_25:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v16,
        (int)a4,
        (struct UnionFs::StackEventTracer *)v18,
        (unsigned __int64)"UnionFs::PostRename",
        v17,
        v58);
      if ( v13 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v13);
LABEL_27:
      wil::details::lambda_call__lambda_e481c12519ae2931117ebb4308fac750___::_lambda_call__lambda_e481c12519ae2931117ebb4308fac750___(&p_Entry);
      v19 = Entry;
      if ( Entry )
      {
        UnionFs::RenameContext::~RenameContext((UnionFs::RenameContext *)Entry);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 320), v19);
      }
      return (unsigned int)v16;
    }
    v22 = UnionFs::g_FilterState;
    *(_BYTE *)(v14 + 208) = 1;
    v23 = v22[15];
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v23 + 8), 1u) )
      KeSetEvent((PRKEVENT)(v23 + 16), 0, 0);
    v24 = UnionFs::g_FilterState;
    *(_BYTE *)(v14 + 296) = 1;
    v25 = v24[16];
    if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v25 + 8), 1u) )
      KeSetEvent((PRKEVENT)(v25 + 16), 0, 0);
    v26 = (__int64 *)Entry;
    if ( *(_QWORD *)Entry )
    {
      if ( *(_WORD *)(*(_QWORD *)Entry + 162LL) == 4 )
      {
        P = 0;
        v27 = UnionFs::UfsPathName::Copy(*(PCUNICODE_STRING *)(*(_QWORD *)Entry + 208LL));
        if ( v27 < 0 )
        {
          v28 = "PUSH: Copying original scratch path";
          v29 = 0x18E000B0412LL;
          goto LABEL_43;
        }
        v27 = UnionFs::UfsPathCachePayload::MarkRenamed(*((_QWORD *)Entry + 2), &P, a4);
        if ( v27 < 0 )
        {
          v28 = "PUSH: Marking renamed";
          v29 = 0x600000B0418LL;
LABEL_43:
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v27,
            (int)a4,
            (struct UnionFs::StackEventTracer *)v29,
            (unsigned __int64)"UnionFs::PostRename",
            v28,
            v58);
          v31 = (struct _UNICODE_STRING *)P;
          if ( P )
          {
            if ( !*((_BYTE *)P + 16) )
              *(_OWORD *)P = 0;
            FsFltWil::Details::FreeUnicodeString(v31, v30);
            ExFreePoolWithTag(v31, 0);
          }
          goto LABEL_47;
        }
        v34 = (struct _UNICODE_STRING *)P;
        if ( P )
        {
          if ( !*((_BYTE *)P + 16) )
            *(_OWORD *)P = 0;
          FsFltWil::Details::FreeUnicodeString(v34, v33);
          ExFreePoolWithTag(v34, 0);
        }
        goto LABEL_58;
      }
      v26 = (__int64 *)Entry;
    }
    v35 = *v26;
    if ( *v26 && (v26 = (__int64 *)Entry, *(_WORD *)(v35 + 162) == 3) )
    {
      v27 = UnionFs::UfsPathCachePayload::MarkReplaced(*((UnionFs::UfsPathCachePayload **)Entry + 2), a4);
      if ( v27 < 0 )
      {
        v36 = "PUSH: Failed to replace tombstone";
        v37 = 0x3F0000B0423LL;
LABEL_65:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v27,
          (int)a4,
          (struct UnionFs::StackEventTracer *)v37,
          (unsigned __int64)"UnionFs::PostRename",
          v36,
          v58);
LABEL_47:
        if ( v13 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v13);
LABEL_49:
        wil::details::lambda_call__lambda_e481c12519ae2931117ebb4308fac750___::_lambda_call__lambda_e481c12519ae2931117ebb4308fac750___(&p_Entry);
        v32 = Entry;
        if ( Entry )
        {
          UnionFs::RenameContext::~RenameContext((UnionFs::RenameContext *)Entry);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 320), v32);
        }
        return (unsigned int)v27;
      }
    }
    else
    {
      v27 = UnionFs::UfsPathCachePayload::MarkRenamed(v26[2], v26 + 4, a4);
      if ( v27 < 0 )
      {
        v36 = "PUSH: Marking renamed";
        v37 = 0x5FF000B042FLL;
        goto LABEL_65;
      }
    }
LABEL_58:
    if ( v13 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v13);
    goto LABEL_101;
  }
  utl::make_unique<UnionFs::FindAndStatResults,,0>(&P);
  v38 = P;
  if ( P )
  {
    v40 = Entry;
    v41 = (volatile signed __int32 *)*((_QWORD *)Entry + 30);
    v42 = *((_QWORD *)Entry + 29);
    if ( v41 )
    {
      _InterlockedIncrement(v41 + 2);
      v40 = Entry;
    }
    v43 = (UnionFs::UfsLayerCtx *)*((_QWORD *)v40 + 8);
    v67 = 0;
    UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(v43, &v67, 1);
    v58 = (char *)a4;
    v44 = ((*(_DWORD *)(a2->IoStatus.Information + 80) >> 17) & 1) == 0;
    v66 = *(_OWORD *)*((_QWORD *)Entry + 5);
    v16 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(v42, &v66, &v67, v44, v38);
    if ( v16 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v16,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x648000B044ELL,
        (unsigned __int64)"UnionFs::PostRename",
        "PUSH: Probing for item in layers",
        (const char *)a4);
      if ( v41 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v41);
      if ( v38 )
      {
        v45 = (utl::_RefCountBase *)v38[11];
        if ( v45 )
          utl::_RefCountBase::_DecStrong(v45);
        ExFreePoolWithTag(v38, 0);
      }
      goto LABEL_27;
    }
    v46 = (UnionFs::UfsPathCachePayload *)*((_QWORD *)Entry + 2);
    if ( v46 )
    {
      v47 = (UnionFs::UfsPathCachePayload *)*((_QWORD *)Entry + 2);
      if ( *(_WORD *)v38 == 1 )
      {
        v27 = UnionFs::UfsPathCachePayload::MarkReplaced(v47, a4);
        if ( v27 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v27,
            (int)a4,
            (struct UnionFs::StackEventTracer *)0x649000B045BLL,
            (unsigned __int64)"UnionFs::PostRename",
            "PUSH: Failed to replace tombstone",
            (const char *)a4);
          if ( v41 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v41);
          if ( v38 )
          {
            v48 = (utl::_RefCountBase *)v38[11];
            if ( v48 )
              utl::_RefCountBase::_DecStrong(v48);
            ExFreePoolWithTag(v38, 0);
          }
          goto LABEL_49;
        }
      }
      else
      {
        UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(v47, 0x64A000B045FLL);
        UnionFs::UfsPathCachePayload::RevertSoftTombstone(v46);
      }
    }
    if ( v41 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v41);
    if ( v38 )
    {
      v49 = (utl::_RefCountBase *)v38[11];
      if ( v49 )
        utl::_RefCountBase::_DecStrong(v49);
      ExFreePoolWithTag(v38, 0);
    }
LABEL_101:
    if ( *(_QWORD *)Entry )
    {
      if ( !*((_QWORD *)Entry + 6) )
        MicrosoftTelemetryAssertTriggeredMsgKM("renameCtx->SourceScratchLayer");
      v51 = UnionFs::UfsPathCachePayload::HardenTombstone(*(UnionFs::UfsPathCachePayload **)Entry, a4, 0);
      if ( v51 < 0 )
      {
        v52 = "PUSH: Failed to harden tombstone";
        v53 = 0x33A000B047DLL;
LABEL_106:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v51,
          (int)a4,
          (struct UnionFs::StackEventTracer *)v53,
          (unsigned __int64)"UnionFs::PostRename",
          v52,
          v58);
        wil::details::lambda_call__lambda_e481c12519ae2931117ebb4308fac750___::_lambda_call__lambda_e481c12519ae2931117ebb4308fac750___(&p_Entry);
        v54 = Entry;
        if ( Entry )
        {
          UnionFs::RenameContext::~RenameContext((UnionFs::RenameContext *)Entry);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 320), v54);
        }
        return (unsigned int)v51;
      }
    }
LABEL_119:
    v65 = 0;
    wil::details::lambda_call__lambda_e481c12519ae2931117ebb4308fac750___::_lambda_call__lambda_e481c12519ae2931117ebb4308fac750___(&p_Entry);
    v57 = Entry;
    if ( Entry )
    {
      UnionFs::RenameContext::~RenameContext((UnionFs::RenameContext *)Entry);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 320), v57);
    }
    return 0;
  }
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC000009ALL,
    (int)a4,
    (struct UnionFs::StackEventTracer *)0x647000B043CLL,
    (unsigned __int64)"UnionFs::PostRename",
    "ORIGIN: Allocating findAndStatResults",
    v58);
  wil::details::lambda_call__lambda_e481c12519ae2931117ebb4308fac750___::_lambda_call__lambda_e481c12519ae2931117ebb4308fac750___(&p_Entry);
  v39 = Entry;
  if ( Entry )
  {
    UnionFs::RenameContext::~RenameContext((UnionFs::RenameContext *)Entry);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 320), v39);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14002c9f0  mov     [rsp-8+arg_8], rbx
0x14002c9f5  push    rbp
0x14002c9f6  push    rsi
0x14002c9f7  push    rdi
0x14002c9f8  push    r12
0x14002c9fa  push    r13
0x14002c9fc  push    r14
0x14002c9fe  push    r15
0x14002ca00  lea     rbp, [rsp-27h]
0x14002ca05  sub     rsp, 0B0h
0x14002ca0c  lea     rax, [rbp+57h+Entry]
0x14002ca10  mov     [rbp+57h+Entry], r8
0x14002ca14  xor     r12d, r12d
0x14002ca17  mov     [rbp+57h+var_68], rax
0x14002ca1b  mov     r14d, 1
0x14002ca21  mov     rax, [r8]
0x14002ca24  mov     rdi, r9
0x14002ca27  mov     r13, rdx
0x14002ca2a  mov     [rbp+57h+var_60], r14b
0x14002ca2e  cmp     [rcx+18h], r12d
0x14002ca32  jnz     loc_14002D218
0x14002ca38  lea     rsi, aUnionfsPostren; "UnionFs::PostRename"
0x14002ca3f  test    rax, rax
0x14002ca42  jz      loc_14002CB1E
0x14002ca48  mov     rax, [r8+20h]
0x14002ca4c  movups  xmm0, xmmword ptr [rax]
0x14002ca4f  movdqu  xmmword ptr [rbp+57h+var_48.Length], xmm0
0x14002ca54  mov     rax, [r8+28h]
0x14002ca58  movups  xmm1, xmmword ptr [rax]
0x14002ca5b  mov     eax, cs:dword_14009E178
0x14002ca61  movdqu  [rbp+57h+var_58], xmm1
0x14002ca66  cmp     eax, 5
0x14002ca69  jbe     loc_14002CB1E
0x14002ca6f  mov     rcx, cs:qword_14009E190
0x14002ca76  mov     rax, cs:qword_14009E188
0x14002ca7d  test    al, 20h
0x14002ca7f  jz      loc_14002CB1E
0x14002ca85  mov     rax, rcx
0x14002ca88  and     eax, 20h
0x14002ca8b  cmp     rax, rcx
0x14002ca8e  jnz     loc_14002CB1E
0x14002ca94  cmp     qword ptr [rbp+57h+var_58+8], r12
0x14002ca98  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x14002ca9f  lea     rax, [rbp+57h+var_58]
0x14002caa3  mov     dword ptr [rbp+57h+P], 3D6h
0x14002caaa  cmovz   rax, rcx
0x14002caae  mov     qword ptr [rbp+57h+var_78], rsi
0x14002cab2  cmp     [rbp+57h+var_48.Buffer], r12
0x14002cab6  lea     rdx, byte_140096BEF
0x14002cabd  mov     [rbp+57h+var_90], rax
0x14002cac1  lea     rax, [rbp+57h+var_48]
0x14002cac5  cmovz   rax, rcx
0x14002cac9  mov     [rbp+57h+var_88], rax
0x14002cacd  lea     rax, aOnecoreBaseFsU_13; "onecore\\base\\fs\\unionfs\\sys\\info.c"...
0x14002cad4  mov     [rbp+57h+var_80], rax
0x14002cad8  lea     rax, aRenamedLayerBa; "Renamed layer-backed file"
0x14002cadf  mov     [rbp+57h+var_70], rax
0x14002cae3  lea     rax, [rbp+57h+var_90]
0x14002cae7  mov     [rsp+0E0h+var_98], rax
0x14002caec  lea     rax, [rbp+57h+var_88]
0x14002caf0  mov     [rsp+0E0h+var_A0], rax
0x14002caf5  lea     rax, [rbp+57h+P]
0x14002caf9  mov     [rsp+0E0h+var_A8], rax
0x14002cafe  lea     rax, [rbp+57h+var_80]
0x14002cb02  mov     [rsp+0E0h+var_B0], rax
0x14002cb07  lea     rax, [rbp+57h+var_78]
0x14002cb0b  mov     [rsp+0E0h+var_B8], rax; char *
0x14002cb10  lea     rax, [rbp+57h+var_70]
0x14002cb14  mov     [rsp+0E0h+var_C0], rax
0x14002cb19  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x14002cb1e  mov     rax, [rbp+57h+Entry]
0x14002cb22  mov     rcx, [rax+40h]
0x14002cb26  test    rcx, rcx
0x14002cb29  jz      loc_14002D166
0x14002cb2f  mov     dl, [rax+180h]
0x14002cb35  test    dl, 2
0x14002cb38  jz      loc_14002D13D
0x14002cb3e  cmp     [rax+30h], rcx
0x14002cb42  jnz     loc_14002CF16
0x14002cb48  test    r14b, dl
0x14002cb4b  jz      loc_14002CF16
0x14002cb51  mov     rax, [rax+10h]
0x14002cb55  test    rax, rax
0x14002cb58  jz      short loc_14002CB68
0x14002cb5a  movzx   eax, word ptr [rax+0A0h]
0x14002cb61  nop
0x14002cb62  cmp     ax, r14w
0x14002cb66  jz      short loc_14002CB74
0x14002cb68  lea     rcx, aRenamectxDestc; "renameCtx->DestCacheEntry && renameCtx-"...
0x14002cb6f  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002cb74  mov     r8, [rbp+57h+Entry]
0x14002cb78  mov     rbx, [r8+0F0h]
0x14002cb7f  mov     r15, [r8+0E8h]
0x14002cb86  test    rbx, rbx
0x14002cb89  jz      short loc_14002CB93
0x14002cb8b  lock inc dword ptr [rbx+8]
0x14002cb8f  mov     r8, [rbp+57h+Entry]
0x14002cb93  cmp     dword ptr [r15+1Ch], 2
0x14002cb98  jnz     short loc_14002CBA4
0x14002cb9a  mov     rax, [r15+20h]
0x14002cb9e  mov     rcx, [rax+10h]
0x14002cba2  jmp     short loc_14002CBAF
0x14002cba4  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002cbab  mov     rcx, [rax+50h]
0x14002cbaf  mov     r9, [r8+28h]
0x14002cbb3  mov     r8, [r8+20h]
0x14002cbb7  mov     rdx, [r13+18h]
0x14002cbbb  mov     dword ptr [rsp+0E0h+var_B8], r12d; char *
0x14002cbc0  mov     [rsp+0E0h+var_C0], rdi
0x14002cbc5  call    ?MoveSubtree@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@1AEAVStackEventTracer@2@W4MoveSubtreeFlags@2@@Z; UnionFs::UfsPathTable::MoveSubtree(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,UnionFs::MoveSubtreeFlags)
0x14002cbca  mov     r12d, eax
0x14002cbcd  test    eax, eax
0x14002cbcf  jns     loc_14002CC6D
0x14002cbd5  lea     rax, aPushMovingSubt; "PUSH: Moving subtree"
0x14002cbdc  mov     r8, 3C10010017Ah; struct UnionFs::StackEventTracer *
0x14002cbe6  lea     r9, aUnionfsUfspath_59; "UnionFs::UfsPathCache::RenameDirectoryE"...
0x14002cbed  mov     [rsp+0E0h+var_C0], rax; char *
0x14002cbf2  mov     rdx, rdi; int
0x14002cbf5  mov     ecx, r12d; this
0x14002cbf8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002cbfd  lea     rax, aPushRenamingEn_0; "PUSH: Renaming entry in path cache"
0x14002cc04  mov     r8, 3C5000B03F4h; struct UnionFs::StackEventTracer *
0x14002cc0e  mov     r9, rsi; unsigned __int64
0x14002cc11  mov     [rsp+0E0h+var_C0], rax; char *
0x14002cc16  mov     rdx, rdi; int
0x14002cc19  mov     ecx, r12d; this
0x14002cc1c  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002cc21  test    rbx, rbx
0x14002cc24  jz      short loc_14002CC2E
0x14002cc26  mov     rcx, rbx; this
0x14002cc29  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002cc2e  lea     rcx, [rbp+57h+var_68]
0x14002cc32  call    wil__details__lambda_call__lambda_e481c12519ae2931117ebb4308fac750______lambda_call__lambda_e481c12519ae2931117ebb4308fac750___
0x14002cc37  mov     rbx, [rbp+57h+Entry]
0x14002cc3b  test    rbx, rbx
0x14002cc3e  jz      short loc_14002CC65
0x14002cc40  mov     rcx, rbx; this
0x14002cc43  call    ??1RenameContext@UnionFs@@QEAA@XZ; UnionFs::RenameContext::~RenameContext(void)
0x14002cc48  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002cc4f  mov     rdx, rbx; Entry
0x14002cc52  add     rcx, 140h; Lookaside
0x14002cc59  call    cs:__imp_ExFreeToLookasideListEx
0x14002cc60  nop     dword ptr [rax+rax+00h]
0x14002cc65  mov     eax, r12d
0x14002cc68  jmp     loc_14002D31A
0x14002cc6d  cmp     dword ptr [r15+1Ch], 2
0x14002cc72  jnz     short loc_14002CC7E
0x14002cc74  mov     rax, [r15+20h]
0x14002cc78  mov     rcx, [rax+18h]
0x14002cc7c  jmp     short loc_14002CC89
0x14002cc7e  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002cc85  mov     rcx, [rax+58h]; this
0x14002cc89  mov     r8, [rbp+57h+Entry]
0x14002cc8d  mov     rdx, [r13+18h]; struct _FLT_INSTANCE *
0x14002cc91  mov     [rsp+0E0h+var_C0], rdi; struct UnionFs::StackEventTracer *
0x14002cc96  mov     r9, [r8+28h]; struct UnionFs::UfsPathName *
0x14002cc9a  mov     r8, [r8+20h]; struct UnionFs::UfsPathName *
0x14002cc9e  call    ?RenameDirectoryEntry@UfsEaTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@1AEAVStackEventTracer@2@@Z; UnionFs::UfsEaTable::RenameDirectoryEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &)
0x14002cca3  mov     r12d, eax
0x14002cca6  test    eax, eax
0x14002cca8  jns     short loc_14002CCC0
0x14002ccaa  lea     rax, aPushRenamingEn; "PUSH: Renaming entry in EA table"
0x14002ccb1  mov     r8, 689000B03FDh
0x14002ccbb  jmp     loc_14002CC0E
0x14002ccc0  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002ccc7  mov     [r15+0D0h], r14b
0x14002ccce  mov     rcx, [rax+78h]
0x14002ccd2  nop
0x14002ccd3  mov     eax, r14d
0x14002ccd6  lock xadd [rcx+8], eax
0x14002ccdb  xor     r12d, r12d
0x14002ccde  nop
0x14002ccdf  test    eax, eax
0x14002cce1  jnz     short loc_14002CCF8
0x14002cce3  add     rcx, 10h; Event
0x14002cce7  xor     r8d, r8d; Wait
0x14002ccea  xor     edx, edx; Increment
0x14002ccec  call    cs:__imp_KeSetEvent
0x14002ccf3  nop     dword ptr [rax+rax+00h]
0x14002ccf8  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002ccff  mov     [r15+128h], r14b
0x14002cd06  mov     rcx, [rax+80h]
0x14002cd0d  nop
0x14002cd0e  lock xadd [rcx+8], r14d
0x14002cd14  nop
0x14002cd15  test    r14d, r14d
0x14002cd18  jnz     short loc_14002CD2F
0x14002cd1a  add     rcx, 10h; Event
0x14002cd1e  xor     r8d, r8d; Wait
0x14002cd21  xor     edx, edx; Increment
0x14002cd23  call    cs:__imp_KeSetEvent
0x14002cd2a  nop     dword ptr [rax+rax+00h]
0x14002cd2f  mov     rcx, [rbp+57h+Entry]
0x14002cd33  mov     rax, [rcx]
0x14002cd36  test    rax, rax
0x14002cd39  jz      loc_14002CE92
0x14002cd3f  movzx   eax, word ptr [rax+0A2h]
0x14002cd46  nop
0x14002cd47  cmp     ax, 4
0x14002cd4b  jnz     loc_14002CE8E
0x14002cd51  mov     rax, [rbp+57h+Entry]
0x14002cd55  lea     rdx, [rbp+57h+P]
0x14002cd59  mov     r8, rdi
0x14002cd5c  mov     [rbp+57h+P], r12
0x14002cd60  mov     rcx, [rax]
0x14002cd63  mov     rcx, [rcx+0D0h]; SourceString
0x14002cd6a  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14002cd6f  mov     r14d, eax
0x14002cd72  test    eax, eax
0x14002cd74  jns     loc_14002CE18
0x14002cd7a  lea     rax, aPushCopyingOri; "PUSH: Copying original scratch path"
0x14002cd81  mov     r8, 18E000B0412h; struct UnionFs::StackEventTracer *
0x14002cd8b  mov     r9, rsi; unsigned __int64
0x14002cd8e  mov     [rsp+0E0h+var_C0], rax; char *
0x14002cd93  mov     rdx, rdi; int
0x14002cd96  mov     ecx, r14d; this
0x14002cd99  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002cd9e  mov     rdi, [rbp+57h+P]
0x14002cda2  test    rdi, rdi
0x14002cda5  jz      short loc_14002CDCC
0x14002cda7  cmp     [rdi+10h], r12b
0x14002cdab  jnz     short loc_14002CDB3
0x14002cdad  xorps   xmm0, xmm0
0x14002cdb0  movups  xmmword ptr [rdi], xmm0
0x14002cdb3  mov     rcx, rdi; UnicodeString
0x14002cdb6  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14002cdbb  xor     edx, edx; Tag
0x14002cdbd  mov     rcx, rdi; P
0x14002cdc0  call    cs:__imp_ExFreePoolWithTag
0x14002cdc7  nop     dword ptr [rax+rax+00h]
0x14002cdcc  test    rbx, rbx
0x14002cdcf  jz      short loc_14002CDD9
0x14002cdd1  mov     rcx, rbx; this
0x14002cdd4  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002cdd9  lea     rcx, [rbp+57h+var_68]
0x14002cddd  call    wil__details__lambda_call__lambda_e481c12519ae2931117ebb4308fac750______lambda_call__lambda_e481c12519ae2931117ebb4308fac750___
0x14002cde2  mov     rbx, [rbp+57h+Entry]
0x14002cde6  test    rbx, rbx
0x14002cde9  jz      short loc_14002CE10
0x14002cdeb  mov     rcx, rbx; this
0x14002cdee  call    ??1RenameContext@UnionFs@@QEAA@XZ; UnionFs::RenameContext::~RenameContext(void)
0x14002cdf3  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002cdfa  mov     rdx, rbx; Entry
0x14002cdfd  add     rcx, 140h; Lookaside
0x14002ce04  call    cs:__imp_ExFreeToLookasideListEx
0x14002ce0b  nop     dword ptr [rax+rax+00h]
0x14002ce10  mov     eax, r14d
0x14002ce13  jmp     loc_14002D31A
0x14002ce18  mov     rcx, [rbp+57h+Entry]
0x14002ce1c  lea     rdx, [rbp+57h+P]
0x14002ce20  mov     r8, rdi
0x14002ce23  mov     rcx, [rcx+10h]
0x14002ce27  call    ?MarkRenamed@UfsPathCachePayload@UnionFs@@QEAAJ$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::MarkRenamed(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::StackEventTracer &)
0x14002ce2c  mov     r14d, eax
0x14002ce2f  test    eax, eax
0x14002ce31  jns     short loc_14002CE49
0x14002ce33  lea     rax, aPushMarkingRen; "PUSH: Marking renamed"
0x14002ce3a  mov     r8, 600000B0418h
0x14002ce44  jmp     loc_14002CD8B
0x14002ce49  mov     r14, [rbp+57h+P]
0x14002ce4d  test    r14, r14
0x14002ce50  jz      short loc_14002CE78
0x14002ce52  cmp     [r14+10h], r12b
0x14002ce56  jnz     short loc_14002CE5F
0x14002ce58  xorps   xmm0, xmm0
0x14002ce5b  movups  xmmword ptr [r14], xmm0
0x14002ce5f  mov     rcx, r14; UnicodeString
0x14002ce62  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14002ce67  xor     edx, edx; Tag
0x14002ce69  mov     rcx, r14; P
0x14002ce6c  call    cs:__imp_ExFreePoolWithTag
0x14002ce73  nop     dword ptr [rax+rax+00h]
0x14002ce78  test    rbx, rbx
0x14002ce7b  jz      loc_14002D17C
0x14002ce81  mov     rcx, rbx; this
0x14002ce84  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002ce89  jmp     loc_14002D17C
0x14002ce8e  mov     rcx, [rbp+57h+Entry]
0x14002ce92  mov     rax, [rcx]
0x14002ce95  test    rax, rax
0x14002ce98  jz      short loc_14002CEE8
0x14002ce9a  movzx   eax, word ptr [rax+0A2h]
0x14002cea1  nop
0x14002cea2  mov     rcx, [rbp+57h+Entry]
0x14002cea6  cmp     ax, 3
0x14002ceaa  jnz     short loc_14002CEE8
0x14002ceac  mov     rcx, [rcx+10h]; this
0x14002ceb0  mov     rdx, rdi; struct UnionFs::StackEventTracer *
0x14002ceb3  call    ?MarkReplaced@UfsPathCachePayload@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::MarkReplaced(UnionFs::StackEventTracer &)
0x14002ceb8  mov     r14d, eax
0x14002cebb  test    eax, eax
0x14002cebd  jns     short loc_14002CE78
0x14002cebf  lea     rax, aPushFailedToRe_0; "PUSH: Failed to replace tombstone"
0x14002cec6  mov     r8, 3F0000B0423h; struct UnionFs::StackEventTracer *
0x14002ced0  mov     r9, rsi; unsigned __int64
0x14002ced3  mov     [rsp+0E0h+var_C0], rax; char *
0x14002ced8  mov     rdx, rdi; int
0x14002cedb  mov     ecx, r14d; this
0x14002cede  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002cee3  jmp     loc_14002CDCC
  ... truncated ...
```
