# UnionFs::PostRename(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,void *,UnionFs::StackEventTracer &)

- ea: `0x14002ca90`
- end: `0x14002d3d6`
- name: `?PostRename@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@PEAXAEAVStackEventTracer@1@@Z`
- size: `2374`
- prototype: `int(UnionFs *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002d3e0`

## callees

- `0x140002878`
- `0x14000f81c`
- `0x140010ba8`
- `0x140023c1c`
- `0x14002bce4`
- `0x14002bf44`
- `0x14002ca90`
- `0x140036268`
- `0x140042328`
- `0x140042674`
- `0x140042b30`
- `0x140042f54`
- `0x14004327c`
- `0x1400435f4`
- `0x1400448c8`
- `0x14004df10`
- `0x140056c44`
- `0x140056c7c`
- `0x1400611a4`
- `0x140079f68`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002ce60`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cf0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d0f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d17f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d1cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ce60`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cf0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d0f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d17f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d1cf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002ccf9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002cea4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d01b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d2a5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d3ac`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002ccf9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002cea4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d01b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d2a5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d3ac`
- `ntoskrnl!KeSetEvent` at `0x14002cd8c`
- `ntoskrnl!KeSetEvent` at `0x14002cdc3`
- `ntoskrnl!KeSetEvent` at `0x14002cd8c`
- `ntoskrnl!KeSetEvent` at `0x14002cdc3`

## string_xrefs

- `0x14002cf5f`: `PUSH: Failed to replace tombstone`
- `0x14002d132`: `PUSH: Failed to replace tombstone`
- `0x14002cad8`: `UnionFs::PostRename`
- `0x14002d2df`: `UnionFs::PostRename`
- `0x14002d34f`: `UnionFs::PostRename`
- `0x14002cb78`: `Renamed layer-backed file`
- `0x14002cc08`: `renameCtx->DestCacheEntry && renameCtx->DestCacheEntry->GetTombstoneState() == TombstoneState::Soft`
- `0x14002cc9d`: `PUSH: Renaming entry in path cache`
- `0x14002ce1a`: `PUSH: Copying original scratch path`
- `0x14002ced3`: `PUSH: Marking renamed`
- `0x14002cfa3`: `PUSH: Marking renamed`
- `0x14002d22f`: `renameCtx->SourceScratchLayer`
- `0x14002d307`: `renameCtx->DestCacheEntry->GetTombstoneState() == TombstoneState::Soft`
- `0x14002cc86`: `UnionFs::UfsPathCache::RenameDirectoryEntry`

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
      if ( *(_WORD *)(v55 + 168) != 1 )
        MicrosoftTelemetryAssertTriggeredMsgKM("renameCtx->DestCacheEntry->GetTombstoneState() == TombstoneState::Soft");
      if ( *(_WORD *)(*((_QWORD *)Entry + 2) + 170LL) )
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
        (unsigned int)byte_140096CB3,
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
    if ( !v11 || *(_WORD *)(v11 + 168) != 1 )
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
      if ( *(_WORD *)(*(_QWORD *)Entry + 170LL) == 4 )
      {
        P = 0;
        v27 = UnionFs::UfsPathName::Copy(*(PCUNICODE_STRING *)(*(_QWORD *)Entry + 216LL));
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
    if ( *v26 && (v26 = (__int64 *)Entry, *(_WORD *)(v35 + 170) == 3) )
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
0x14002ca90  mov     [rsp-8+arg_8], rbx
0x14002ca95  push    rbp
0x14002ca96  push    rsi
0x14002ca97  push    rdi
0x14002ca98  push    r12
0x14002ca9a  push    r13
0x14002ca9c  push    r14
0x14002ca9e  push    r15
0x14002caa0  lea     rbp, [rsp-27h]
0x14002caa5  sub     rsp, 0B0h
0x14002caac  lea     rax, [rbp+57h+Entry]
0x14002cab0  mov     [rbp+57h+Entry], r8
0x14002cab4  xor     r12d, r12d
0x14002cab7  mov     [rbp+57h+var_68], rax
0x14002cabb  mov     r14d, 1
0x14002cac1  mov     rax, [r8]
0x14002cac4  mov     rdi, r9
0x14002cac7  mov     r13, rdx
0x14002caca  mov     [rbp+57h+var_60], r14b
0x14002cace  cmp     [rcx+18h], r12d
0x14002cad2  jnz     loc_14002D2B8
0x14002cad8  lea     rsi, aUnionfsPostren; "UnionFs::PostRename"
0x14002cadf  test    rax, rax
0x14002cae2  jz      loc_14002CBBE
0x14002cae8  mov     rax, [r8+20h]
0x14002caec  movups  xmm0, xmmword ptr [rax]
0x14002caef  movdqu  xmmword ptr [rbp+57h+var_48.Length], xmm0
0x14002caf4  mov     rax, [r8+28h]
0x14002caf8  movups  xmm1, xmmword ptr [rax]
0x14002cafb  mov     eax, cs:dword_14009E178
0x14002cb01  movdqu  [rbp+57h+var_58], xmm1
0x14002cb06  cmp     eax, 5
0x14002cb09  jbe     loc_14002CBBE
0x14002cb0f  mov     rcx, cs:qword_14009E190
0x14002cb16  mov     rax, cs:qword_14009E188
0x14002cb1d  test    al, 20h
0x14002cb1f  jz      loc_14002CBBE
0x14002cb25  mov     rax, rcx
0x14002cb28  and     eax, 20h
0x14002cb2b  cmp     rax, rcx
0x14002cb2e  jnz     loc_14002CBBE
0x14002cb34  cmp     qword ptr [rbp+57h+var_58+8], r12
0x14002cb38  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x14002cb3f  lea     rax, [rbp+57h+var_58]
0x14002cb43  mov     dword ptr [rbp+57h+P], 3D6h
0x14002cb4a  cmovz   rax, rcx
0x14002cb4e  mov     qword ptr [rbp+57h+var_78], rsi
0x14002cb52  cmp     [rbp+57h+var_48.Buffer], r12
0x14002cb56  lea     rdx, byte_140096CB3
0x14002cb5d  mov     [rbp+57h+var_90], rax
0x14002cb61  lea     rax, [rbp+57h+var_48]
0x14002cb65  cmovz   rax, rcx
0x14002cb69  mov     [rbp+57h+var_88], rax
0x14002cb6d  lea     rax, aOnecoreBaseFsU_13; "onecore\\base\\fs\\unionfs\\sys\\info.c"...
0x14002cb74  mov     [rbp+57h+var_80], rax
0x14002cb78  lea     rax, aRenamedLayerBa; "Renamed layer-backed file"
0x14002cb7f  mov     [rbp+57h+var_70], rax
0x14002cb83  lea     rax, [rbp+57h+var_90]
0x14002cb87  mov     [rsp+0E0h+var_98], rax
0x14002cb8c  lea     rax, [rbp+57h+var_88]
0x14002cb90  mov     [rsp+0E0h+var_A0], rax
0x14002cb95  lea     rax, [rbp+57h+P]
0x14002cb99  mov     [rsp+0E0h+var_A8], rax
0x14002cb9e  lea     rax, [rbp+57h+var_80]
0x14002cba2  mov     [rsp+0E0h+var_B0], rax
0x14002cba7  lea     rax, [rbp+57h+var_78]
0x14002cbab  mov     [rsp+0E0h+var_B8], rax; char *
0x14002cbb0  lea     rax, [rbp+57h+var_70]
0x14002cbb4  mov     [rsp+0E0h+var_C0], rax
0x14002cbb9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x14002cbbe  mov     rax, [rbp+57h+Entry]
0x14002cbc2  mov     rcx, [rax+40h]
0x14002cbc6  test    rcx, rcx
0x14002cbc9  jz      loc_14002D206
0x14002cbcf  mov     dl, [rax+180h]
0x14002cbd5  test    dl, 2
0x14002cbd8  jz      loc_14002D1DD
0x14002cbde  cmp     [rax+30h], rcx
0x14002cbe2  jnz     loc_14002CFB6
0x14002cbe8  test    r14b, dl
0x14002cbeb  jz      loc_14002CFB6
0x14002cbf1  mov     rax, [rax+10h]
0x14002cbf5  test    rax, rax
0x14002cbf8  jz      short loc_14002CC08
0x14002cbfa  movzx   eax, word ptr [rax+0A8h]
0x14002cc01  nop
0x14002cc02  cmp     ax, r14w
0x14002cc06  jz      short loc_14002CC14
0x14002cc08  lea     rcx, aRenamectxDestc; "renameCtx->DestCacheEntry && renameCtx-"...
0x14002cc0f  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002cc14  mov     r8, [rbp+57h+Entry]
0x14002cc18  mov     rbx, [r8+0F0h]
0x14002cc1f  mov     r15, [r8+0E8h]
0x14002cc26  test    rbx, rbx
0x14002cc29  jz      short loc_14002CC33
0x14002cc2b  lock inc dword ptr [rbx+8]
0x14002cc2f  mov     r8, [rbp+57h+Entry]
0x14002cc33  cmp     dword ptr [r15+1Ch], 2
0x14002cc38  jnz     short loc_14002CC44
0x14002cc3a  mov     rax, [r15+20h]
0x14002cc3e  mov     rcx, [rax+10h]
0x14002cc42  jmp     short loc_14002CC4F
0x14002cc44  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002cc4b  mov     rcx, [rax+50h]
0x14002cc4f  mov     r9, [r8+28h]
0x14002cc53  mov     r8, [r8+20h]
0x14002cc57  mov     rdx, [r13+18h]
0x14002cc5b  mov     dword ptr [rsp+0E0h+var_B8], r12d; char *
0x14002cc60  mov     [rsp+0E0h+var_C0], rdi
0x14002cc65  call    ?MoveSubtree@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@1AEAVStackEventTracer@2@W4MoveSubtreeFlags@2@@Z; UnionFs::UfsPathTable::MoveSubtree(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,UnionFs::MoveSubtreeFlags)
0x14002cc6a  mov     r12d, eax
0x14002cc6d  test    eax, eax
0x14002cc6f  jns     loc_14002CD0D
0x14002cc75  lea     rax, aPushMovingSubt; "PUSH: Moving subtree"
0x14002cc7c  mov     r8, 3C10010017Ah; struct UnionFs::StackEventTracer *
0x14002cc86  lea     r9, aUnionfsUfspath_59; "UnionFs::UfsPathCache::RenameDirectoryE"...
0x14002cc8d  mov     [rsp+0E0h+var_C0], rax; char *
0x14002cc92  mov     rdx, rdi; int
0x14002cc95  mov     ecx, r12d; this
0x14002cc98  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002cc9d  lea     rax, aPushRenamingEn_0; "PUSH: Renaming entry in path cache"
0x14002cca4  mov     r8, 3C5000B03F4h; struct UnionFs::StackEventTracer *
0x14002ccae  mov     r9, rsi; unsigned __int64
0x14002ccb1  mov     [rsp+0E0h+var_C0], rax; char *
0x14002ccb6  mov     rdx, rdi; int
0x14002ccb9  mov     ecx, r12d; this
0x14002ccbc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002ccc1  test    rbx, rbx
0x14002ccc4  jz      short loc_14002CCCE
0x14002ccc6  mov     rcx, rbx; this
0x14002ccc9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002ccce  lea     rcx, [rbp+57h+var_68]
0x14002ccd2  call    wil__details__lambda_call__lambda_e481c12519ae2931117ebb4308fac750______lambda_call__lambda_e481c12519ae2931117ebb4308fac750___
0x14002ccd7  mov     rbx, [rbp+57h+Entry]
0x14002ccdb  test    rbx, rbx
0x14002ccde  jz      short loc_14002CD05
0x14002cce0  mov     rcx, rbx; this
0x14002cce3  call    ??1RenameContext@UnionFs@@QEAA@XZ; UnionFs::RenameContext::~RenameContext(void)
0x14002cce8  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002ccef  mov     rdx, rbx; Entry
0x14002ccf2  add     rcx, 140h; Lookaside
0x14002ccf9  call    cs:__imp_ExFreeToLookasideListEx
0x14002cd00  nop     dword ptr [rax+rax+00h]
0x14002cd05  mov     eax, r12d
0x14002cd08  jmp     loc_14002D3BA
0x14002cd0d  cmp     dword ptr [r15+1Ch], 2
0x14002cd12  jnz     short loc_14002CD1E
0x14002cd14  mov     rax, [r15+20h]
0x14002cd18  mov     rcx, [rax+18h]
0x14002cd1c  jmp     short loc_14002CD29
0x14002cd1e  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002cd25  mov     rcx, [rax+58h]; this
0x14002cd29  mov     r8, [rbp+57h+Entry]
0x14002cd2d  mov     rdx, [r13+18h]; struct _FLT_INSTANCE *
0x14002cd31  mov     [rsp+0E0h+var_C0], rdi; struct UnionFs::StackEventTracer *
0x14002cd36  mov     r9, [r8+28h]; struct UnionFs::UfsPathName *
0x14002cd3a  mov     r8, [r8+20h]; struct UnionFs::UfsPathName *
0x14002cd3e  call    ?RenameDirectoryEntry@UfsEaTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@1AEAVStackEventTracer@2@@Z; UnionFs::UfsEaTable::RenameDirectoryEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &)
0x14002cd43  mov     r12d, eax
0x14002cd46  test    eax, eax
0x14002cd48  jns     short loc_14002CD60
0x14002cd4a  lea     rax, aPushRenamingEn; "PUSH: Renaming entry in EA table"
0x14002cd51  mov     r8, 689000B03FDh
0x14002cd5b  jmp     loc_14002CCAE
0x14002cd60  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002cd67  mov     [r15+0D0h], r14b
0x14002cd6e  mov     rcx, [rax+78h]
0x14002cd72  nop
0x14002cd73  mov     eax, r14d
0x14002cd76  lock xadd [rcx+8], eax
0x14002cd7b  xor     r12d, r12d
0x14002cd7e  nop
0x14002cd7f  test    eax, eax
0x14002cd81  jnz     short loc_14002CD98
0x14002cd83  add     rcx, 10h; Event
0x14002cd87  xor     r8d, r8d; Wait
0x14002cd8a  xor     edx, edx; Increment
0x14002cd8c  call    cs:__imp_KeSetEvent
0x14002cd93  nop     dword ptr [rax+rax+00h]
0x14002cd98  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002cd9f  mov     [r15+128h], r14b
0x14002cda6  mov     rcx, [rax+80h]
0x14002cdad  nop
0x14002cdae  lock xadd [rcx+8], r14d
0x14002cdb4  nop
0x14002cdb5  test    r14d, r14d
0x14002cdb8  jnz     short loc_14002CDCF
0x14002cdba  add     rcx, 10h; Event
0x14002cdbe  xor     r8d, r8d; Wait
0x14002cdc1  xor     edx, edx; Increment
0x14002cdc3  call    cs:__imp_KeSetEvent
0x14002cdca  nop     dword ptr [rax+rax+00h]
0x14002cdcf  mov     rcx, [rbp+57h+Entry]
0x14002cdd3  mov     rax, [rcx]
0x14002cdd6  test    rax, rax
0x14002cdd9  jz      loc_14002CF32
0x14002cddf  movzx   eax, word ptr [rax+0AAh]
0x14002cde6  nop
0x14002cde7  cmp     ax, 4
0x14002cdeb  jnz     loc_14002CF2E
0x14002cdf1  mov     rax, [rbp+57h+Entry]
0x14002cdf5  lea     rdx, [rbp+57h+P]
0x14002cdf9  mov     r8, rdi
0x14002cdfc  mov     [rbp+57h+P], r12
0x14002ce00  mov     rcx, [rax]
0x14002ce03  mov     rcx, [rcx+0D8h]; SourceString
0x14002ce0a  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14002ce0f  mov     r14d, eax
0x14002ce12  test    eax, eax
0x14002ce14  jns     loc_14002CEB8
0x14002ce1a  lea     rax, aPushCopyingOri; "PUSH: Copying original scratch path"
0x14002ce21  mov     r8, 18E000B0412h; struct UnionFs::StackEventTracer *
0x14002ce2b  mov     r9, rsi; unsigned __int64
0x14002ce2e  mov     [rsp+0E0h+var_C0], rax; char *
0x14002ce33  mov     rdx, rdi; int
0x14002ce36  mov     ecx, r14d; this
0x14002ce39  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002ce3e  mov     rdi, [rbp+57h+P]
0x14002ce42  test    rdi, rdi
0x14002ce45  jz      short loc_14002CE6C
0x14002ce47  cmp     [rdi+10h], r12b
0x14002ce4b  jnz     short loc_14002CE53
0x14002ce4d  xorps   xmm0, xmm0
0x14002ce50  movups  xmmword ptr [rdi], xmm0
0x14002ce53  mov     rcx, rdi; UnicodeString
0x14002ce56  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14002ce5b  xor     edx, edx; Tag
0x14002ce5d  mov     rcx, rdi; P
0x14002ce60  call    cs:__imp_ExFreePoolWithTag
0x14002ce67  nop     dword ptr [rax+rax+00h]
0x14002ce6c  test    rbx, rbx
0x14002ce6f  jz      short loc_14002CE79
0x14002ce71  mov     rcx, rbx; this
0x14002ce74  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002ce79  lea     rcx, [rbp+57h+var_68]
0x14002ce7d  call    wil__details__lambda_call__lambda_e481c12519ae2931117ebb4308fac750______lambda_call__lambda_e481c12519ae2931117ebb4308fac750___
0x14002ce82  mov     rbx, [rbp+57h+Entry]
0x14002ce86  test    rbx, rbx
0x14002ce89  jz      short loc_14002CEB0
0x14002ce8b  mov     rcx, rbx; this
0x14002ce8e  call    ??1RenameContext@UnionFs@@QEAA@XZ; UnionFs::RenameContext::~RenameContext(void)
0x14002ce93  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002ce9a  mov     rdx, rbx; Entry
0x14002ce9d  add     rcx, 140h; Lookaside
0x14002cea4  call    cs:__imp_ExFreeToLookasideListEx
0x14002ceab  nop     dword ptr [rax+rax+00h]
0x14002ceb0  mov     eax, r14d
0x14002ceb3  jmp     loc_14002D3BA
0x14002ceb8  mov     rcx, [rbp+57h+Entry]
0x14002cebc  lea     rdx, [rbp+57h+P]
0x14002cec0  mov     r8, rdi
0x14002cec3  mov     rcx, [rcx+10h]
0x14002cec7  call    ?MarkRenamed@UfsPathCachePayload@UnionFs@@QEAAJ$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::MarkRenamed(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::StackEventTracer &)
0x14002cecc  mov     r14d, eax
0x14002cecf  test    eax, eax
0x14002ced1  jns     short loc_14002CEE9
0x14002ced3  lea     rax, aPushMarkingRen; "PUSH: Marking renamed"
0x14002ceda  mov     r8, 600000B0418h
0x14002cee4  jmp     loc_14002CE2B
0x14002cee9  mov     r14, [rbp+57h+P]
0x14002ceed  test    r14, r14
0x14002cef0  jz      short loc_14002CF18
0x14002cef2  cmp     [r14+10h], r12b
0x14002cef6  jnz     short loc_14002CEFF
0x14002cef8  xorps   xmm0, xmm0
0x14002cefb  movups  xmmword ptr [r14], xmm0
0x14002ceff  mov     rcx, r14; UnicodeString
0x14002cf02  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14002cf07  xor     edx, edx; Tag
0x14002cf09  mov     rcx, r14; P
0x14002cf0c  call    cs:__imp_ExFreePoolWithTag
0x14002cf13  nop     dword ptr [rax+rax+00h]
0x14002cf18  test    rbx, rbx
0x14002cf1b  jz      loc_14002D21C
0x14002cf21  mov     rcx, rbx; this
0x14002cf24  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002cf29  jmp     loc_14002D21C
0x14002cf2e  mov     rcx, [rbp+57h+Entry]
0x14002cf32  mov     rax, [rcx]
0x14002cf35  test    rax, rax
0x14002cf38  jz      short loc_14002CF88
0x14002cf3a  movzx   eax, word ptr [rax+0AAh]
0x14002cf41  nop
0x14002cf42  mov     rcx, [rbp+57h+Entry]
0x14002cf46  cmp     ax, 3
0x14002cf4a  jnz     short loc_14002CF88
0x14002cf4c  mov     rcx, [rcx+10h]; this
0x14002cf50  mov     rdx, rdi; struct UnionFs::StackEventTracer *
0x14002cf53  call    ?MarkReplaced@UfsPathCachePayload@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::MarkReplaced(UnionFs::StackEventTracer &)
0x14002cf58  mov     r14d, eax
0x14002cf5b  test    eax, eax
0x14002cf5d  jns     short loc_14002CF18
0x14002cf5f  lea     rax, aPushFailedToRe_0; "PUSH: Failed to replace tombstone"
0x14002cf66  mov     r8, 3F0000B0423h; struct UnionFs::StackEventTracer *
0x14002cf70  mov     r9, rsi; unsigned __int64
0x14002cf73  mov     [rsp+0E0h+var_C0], rax; char *
0x14002cf78  mov     rdx, rdi; int
0x14002cf7b  mov     ecx, r14d; this
0x14002cf7e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002cf83  jmp     loc_14002CE6C
  ... truncated ...
```
