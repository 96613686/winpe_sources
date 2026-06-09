# CmsAllocator::AllocateAndCopy(CmsTransactionContext *,_LCN_TUPLE *,SmsPage *)

- ea: `0x14006ec00`
- end: `0x14006f7f8`
- name: `?AllocateAndCopy@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@PEAT_LCN_TUPLE@@PEAUSmsPage@@@Z`
- size: `3064`
- prototype: `int(CmsAllocator *__hidden this, struct CmsTransactionContext *, union _LCN_TUPLE *, struct SmsPage *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006dad0`

## callees

- `0x14000f670`
- `0x140016440`
- `0x14001c620`
- `0x140021490`
- `0x140021b90`
- `0x14002dd70`
- `0x14003b6a0`
- `0x14003f2b0`
- `0x1400680f0`
- `0x140068ef0`
- `0x14006ec00`
- `0x140075434`
- `0x14007b2a0`
- `0x140080160`
- `0x140083220`
- `0x1400854c0`
- `0x140088930`
- `0x14008ab10`
- `0x140091520`
- `0x140097cf0`
- `0x140098ea0`
- `0x140099270`
- `0x1400abaac`
- `0x1400be1fc`
- `0x1400cb544`
- `0x1400cbe48`
- `0x1400ceda0`
- `0x14011ac34`
- `0x140122d34`
- `0x140125358`
- `0x14012ad7c`
- `0x1401f3fc0`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14006ec9c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ed04`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006ed04`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006eccc`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006eccc`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x14006f555`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x14006f555`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006ed12`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14006ed12`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14006f679`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x14006f679`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockExclusive` at `0x14006f5b9`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockExclusive` at `0x14006f5b9`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006ed4d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14006ed4d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006eea8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006eea8`
- `ntoskrnl!KeInitializeEvent` at `0x14006ee55`
- `ntoskrnl!KeInitializeEvent` at `0x14006ee55`

## string_xrefs

- `0x14006f7eb`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsAllocator::AllocateAndCopy(
        CmsAllocator *this,
        struct CmsTransactionContext *a2,
        union _LCN_TUPLE *a3,
        struct SmsPage *a4)
{
  CmsBPlusTable *v4; // rdi
  char v6; // al
  union _LCN_TUPLE *v9; // r13
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r8
  const struct std::nothrow_t *v13; // rdx
  unsigned int v14; // r8d
  __int64 v15; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v16; // rcx
  struct SmsUndoRecord *v17; // rax
  struct SmsUndoRecord *v18; // r14
  int v19; // ecx
  unsigned __int64 v20; // rcx
  struct SmsUndoRecord *v21; // rax
  int v22; // esi
  struct CmsVolume *v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // r8
  SmsPage *v26; // rdi
  char v27; // r13
  int inserted; // eax
  unsigned __int8 v29; // al
  bool v30; // bl
  bool IsPageStateAbandoned; // al
  struct CmsVolume *v32; // rbx
  __int64 v33; // rcx
  unsigned __int8 IsDirty; // al
  unsigned __int64 v35; // rcx
  __int64 v36; // rax
  void *v37; // r9
  unsigned __int16 v38; // di
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int64 v41; // rcx
  __int64 v42; // rax
  int v43; // ecx
  unsigned int v44; // r10d
  __int64 v45; // rdx
  __int64 i; // r8
  int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rax
  char IsPageStateNew; // al
  unsigned __int8 HasGlobalBindingSemantics; // al
  CmsBPlusTable *j; // rdx
  CmsVolume *v53; // rsi
  unsigned int v54; // r9d
  SmsPage *v55; // r13
  unsigned int v56; // ebx
  _DWORD *v57; // rdx
  int *v58; // rcx
  int v59; // eax
  bool v60; // zf
  int v61; // edi
  struct SmsUndoRecord *v62; // r13
  void *v63; // rbx
  SmsPage *v64; // r13
  CmsCachedPin *v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rax
  void *v68; // rbx
  struct SmsPage *v69; // r10
  unsigned int v70; // r9d
  CmsVolume *v71; // r14
  struct SmsPage *v72; // rdi
  unsigned int v73; // ebx
  _DWORD *v74; // rcx
  int *v75; // rdx
  int v76; // eax
  char v78; // [rsp+60h] [rbp-A0h]
  char v79; // [rsp+61h] [rbp-9Fh]
  char v80; // [rsp+62h] [rbp-9Eh]
  SmsPage *v81; // [rsp+68h] [rbp-98h] BYREF
  int Page; // [rsp+70h] [rbp-90h]
  unsigned int v83; // [rsp+78h] [rbp-88h]
  int v84; // [rsp+7Ch] [rbp-84h]
  struct CmsVolume *v85; // [rsp+80h] [rbp-80h]
  CmsBPlusTable *v86; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v87; // [rsp+90h] [rbp-70h]
  __int64 v88; // [rsp+98h] [rbp-68h]
  char v89; // [rsp+A0h] [rbp-60h]
  union _LCN_TUPLE *v90; // [rsp+A8h] [rbp-58h]
  struct SmsUndoRecord *v91; // [rsp+B0h] [rbp-50h]
  struct SmsPage *v92; // [rsp+B8h] [rbp-48h] BYREF
  struct SmsUndoRecord *Undo; // [rsp+C0h] [rbp-40h]
  SmsPage *v94; // [rsp+C8h] [rbp-38h]
  struct SmsPage *v95; // [rsp+D0h] [rbp-30h]
  SmsPage *v96; // [rsp+D8h] [rbp-28h]
  _OWORD v97[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD Event[2]; // [rsp+100h] [rbp+0h] BYREF

  v4 = (CmsBPlusTable *)*((_QWORD *)a4 + 12);
  v6 = *((_BYTE *)a4 + 392);
  v88 = 0;
  v86 = v4;
  v9 = a3;
  v10 = *(_QWORD *)a2;
  v87 = 0;
  v89 = v6;
  v11 = *((_QWORD *)v4 + 20);
  v96 = a4;
  v90 = a3;
  v88 = v11;
  if ( (v10 & 0x800) != 0 && (v10 & 0x200) == 0 )
    v88 = *((_QWORD *)v4 + 21);
  v12 = 0;
  v95 = 0;
  v94 = 0;
  if ( (v10 & 0x1000) != 0 )
  {
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    LOBYTE(v12) = 1;
    CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)a2 + 1), 0x20000000, v12);
    goto LABEL_28;
  }
  v85 = (struct CmsVolume *)*((_QWORD *)this + 57);
  v13 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v15 = qword_140269410 + 192LL * (_QWORD)v13;
  if ( *(_DWORD *)v15 < 0x78u )
  {
    v15 = 0;
    goto LABEL_23;
  }
  if ( *(_BYTE *)(v15 + 8) )
  {
    v16 = (struct _NPAGED_LOOKASIDE_LIST *)(v15 + 64);
    if ( *(_BYTE *)(v15 + 9) )
      v17 = (struct SmsUndoRecord *)ExAllocateFromNPagedLookasideList(v16);
    else
      v17 = (struct SmsUndoRecord *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v16);
    goto LABEL_13;
  }
  if ( (int)*(_QWORD *)(v15 + 88) <= (int)HIDWORD(*(_QWORD *)(v15 + 88)) )
    goto LABEL_20;
  v19 = _InterlockedDecrement((volatile signed __int32 *)(v15 + 88));
  if ( v19 >= *(_DWORD *)(v15 + 92) && v19 >= 0 )
  {
    v17 = (struct SmsUndoRecord *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v15 + 64));
LABEL_13:
    v18 = v17;
    goto LABEL_19;
  }
  v18 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v15 + 88));
LABEL_19:
  if ( !v18 )
  {
LABEL_20:
    if ( v15 )
    {
      v20 = *(unsigned int *)(v15 + 4);
      goto LABEL_24;
    }
LABEL_23:
    v20 = 136;
LABEL_24:
    v21 = (struct SmsUndoRecord *)operator new(v20, v13);
    v91 = v21;
    v18 = v21;
    if ( ((unsigned __int8)v21 & 0xF) != 0 )
      MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
    if ( !v21 )
      goto LABEL_27;
  }
  *(_QWORD *)v18 = v15;
  v18 = (struct SmsUndoRecord *)((char *)v18 + 16);
  v91 = v18;
LABEL_27:
  if ( !v18 )
  {
LABEL_28:
    v18 = 0;
LABEL_29:
    v22 = -1073741670;
LABEL_151:
    CmsBPlusTable::FreeUndoRecord(v18, v13, v14);
    goto LABEL_152;
  }
  *((_DWORD *)v18 + 4) = 1;
  *((_DWORD *)v18 + 3) = 32;
  *((_DWORD *)v18 + 2) = 32;
  *((_QWORD *)v18 + 5) = v4;
  *((_WORD *)v18 + 10) = 0;
  *((_OWORD *)v18 + 3) = 0;
  *((_OWORD *)v18 + 4) = 0;
  *((_QWORD *)v18 + 10) = 0;
  *((_QWORD *)v18 + 3) = (char *)v18 + 88;
  *((_DWORD *)v18 + 8) = 0;
  *(_OWORD *)((char *)v18 + 88) = 0;
  *(_OWORD *)((char *)v18 + 104) = 0;
  v83 = *((_DWORD *)a4 + 94);
  Undo = (struct SmsUndoRecord *)CmsBPlusTable::AllocateUndo(v86, a2, 13);
  if ( !Undo )
    goto LABEL_29;
  v84 = 0;
  while ( 1 )
  {
    v81 = 0;
    v92 = 0;
    *(_QWORD *)&Event[0] = 0;
    KeInitializeEvent((PRKEVENT)((char *)Event + 8), NotificationEvent, 0);
    v23 = v85;
    v22 = CmsVolume::LookupPageTableEntry(v85, a2, v86, v9, (struct SmsWaitListEntry *)Event, &v81);
    if ( v22 == -1073739772 )
    {
      KeWaitForSingleObject((char *)Event + 8, Executive, 0, 0, 0);
      v78 = 1;
      goto LABEL_135;
    }
    v26 = v81;
    v22 = 0;
    v79 = 0;
    v27 = 0;
    v78 = 0;
    if ( !v81 )
    {
      if ( (*((_DWORD *)v23 + 849) & 0x20000000) != 0 )
      {
        v22 = -1073741202;
        goto LABEL_135;
      }
      if ( CmsBPlusTable::AreWritesDoomed(v86, 0, 0) )
      {
        v22 = -1073741823;
        goto LABEL_135;
      }
      inserted = CmsVolume::InsertNewPageTableEntry(v23, a2, (struct SmsView *)&v86, v90, v83, 1u, 1u, &v92);
      Page = inserted;
      v22 = inserted;
      if ( inserted == -1073741771 )
      {
        v22 = -1073739772;
        v78 = 1;
        Page = -1073739772;
LABEL_48:
        v80 = 0;
        goto LABEL_117;
      }
      if ( inserted < 0 )
      {
        v78 = 0;
        goto LABEL_48;
      }
      v26 = v92;
      v22 = 0;
      v81 = v92;
      v27 = 1;
      v78 = 0;
      v79 = 1;
    }
    v80 = 1;
    if ( *((_BYTE *)v26 + 392) != v89 )
      goto LABEL_113;
    if ( !v27 )
    {
      Page = SmsPage::AcquirePageLock(v26, a2, 1, 0);
      v22 = Page;
      if ( Page < 0 )
      {
        _InterlockedIncrement(&dword_140269560);
        goto LABEL_117;
      }
      v26 = v81;
      v27 = 1;
      v22 = 0;
    }
    if ( (*(_QWORD *)a2 & 2) == 0 && (*(_QWORD *)a2 & 0x1000LL) == 0 )
    {
      if ( (*((_DWORD *)v23 + 849) & 0x20000000) != 0 )
      {
        v22 = -1073741202;
        goto LABEL_114;
      }
      v29 = CmsBPlusTable::AreWritesDoomed(v86, 0, 0);
      v26 = v81;
      if ( v29 )
      {
        v22 = -1073741823;
        goto LABEL_114;
      }
    }
    v30 = 0;
    if ( v87 )
      v30 = *v87 < *((_QWORD *)v26 + 44);
    if ( (*(_DWORD *)a2 & 0x800LL) == 0 )
    {
      if ( SmsPage::IsPageStateMapped(v26) )
        SmsPage::IsPageStateResident(v81);
      v26 = v81;
    }
    if ( v30 )
      goto LABEL_113;
    if ( SmsPage::IsDeleted(v26, (const struct SmsView *)&v86) )
    {
      v26 = v81;
LABEL_113:
      v22 = -1073741738;
LABEL_114:
      Page = v22;
      goto LABEL_115;
    }
    IsPageStateAbandoned = SmsPage::IsPageStateAbandoned(v81);
    v26 = v81;
    if ( IsPageStateAbandoned )
    {
      v78 = 1;
      goto LABEL_113;
    }
    if ( (*((_DWORD *)v81 + 138) & 4) != 0 )
    {
      v32 = v85;
      if ( *((_DWORD *)v85 + 796) <= 1u )
        goto LABEL_96;
      if ( *((CmsBPlusTable **)a2 + 422) != v86 )
        goto LABEL_96;
      v33 = *((_QWORD *)a2 + 423);
      if ( v33 )
      {
        if ( *(_BYTE *)(v33 + 6) < 0xAu && *(_QWORD *)v81 == *(_QWORD *)(v33 + 8LL * *(unsigned __int8 *)(v33 + 6) + 24) )
          goto LABEL_96;
      }
      IsDirty = SmsPage::IsDirty(v81, (const struct SmsView *)&v86);
      v26 = v81;
      if ( IsDirty )
        goto LABEL_96;
      v35 = *((_QWORD *)v81 + 42);
      if ( v35 >= 2 )
      {
        v36 = v88 - 1;
        if ( v88 == 1 )
          v36 = *(_QWORD *)(*((_QWORD *)v81 + 12) + 160LL);
        if ( v35 == v36 )
          goto LABEL_96;
      }
      if ( SmsPage::IsPageStateWriting(v81) )
      {
        v26 = v81;
LABEL_96:
        v24 = *((_QWORD *)a2 + 423);
        if ( v24 )
        {
          if ( *((CmsBPlusTable **)a2 + 422) == v86 )
          {
            v49 = *(unsigned __int8 *)(v24 + 6);
            if ( (unsigned __int8)v49 >= 0xAu || *(_QWORD *)v26 != *(_QWORD *)(v24 + 8 * v49 + 24) )
            {
              *(_QWORD *)(v24 + 864) += *((unsigned int *)v26 + 80);
              goto LABEL_105;
            }
          }
        }
        goto LABEL_106;
      }
      CmsTransactionContext::GetScrubBuffer(a2, *((_DWORD *)v81 + 80));
      v37 = (void *)*((_QWORD *)a2 + 424);
      if ( !v37 )
        goto LABEL_105;
      v38 = *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 423) + 856LL) + 4LL);
      v39 = *(_OWORD *)v81;
      Event[0] = *(_OWORD *)v81;
      v40 = *((_OWORD *)v81 + 1);
      Event[1] = v40;
      if ( (*(_BYTE *)(*((_QWORD *)v81 + 12) + 16LL) & 4) != 0 )
        goto LABEL_82;
      v41 = *((_QWORD *)v32 + 409);
      v97[0] = v39;
      v97[1] = v40;
      Page = CmsVolumeContainer::PinContainerRange(v41, a2, v97, Event);
      v22 = Page;
      if ( Page >= 0 )
      {
        v37 = (void *)*((_QWORD *)a2 + 424);
        v22 = 0;
LABEL_82:
        v42 = *((_QWORD *)a2 + 423);
        v43 = *(_DWORD *)(v42 + 792);
        v44 = v43 & 1 | 2;
        if ( (v43 & 8) == 0 )
          v44 = v43 & 1;
        v45 = *((_QWORD *)v86 + 4);
        for ( i = v45; *(_QWORD *)(i + 64) != i; i = *(_QWORD *)(i + 64) )
          ;
        v32 = v85;
        v47 = CmsVolume::SmartIoScrubPage(
                v85,
                *(void **)(*(_QWORD *)(v45 + 40) + 72LL),
                (union SmsBigIdentifier *)(*(_QWORD *)(i + 72) + 376LL),
                (const union _LCN_TUPLE *)Event,
                v37,
                0,
                0,
                v44,
                *(struct _SmsScrubIoOutput **)(v42 + 848),
                *(struct _SCRUB_PARITY_EXTENT_DATA **)(v42 + 856),
                0,
                0);
        v25 = *((_QWORD *)a2 + 423);
        *(_QWORD *)(v25 + 864) += *(_QWORD *)(*(_QWORD *)(v25 + 848) + 24LL);
        if ( v47 >= 0 )
        {
          v25 = *((_QWORD *)a2 + 423);
          if ( v25 )
          {
            if ( *(_BYTE *)(v25 + 6) < 0xAu )
              *(_QWORD *)(v25 + 8LL * *(unsigned __int8 *)(v25 + 6) + 24) = *(_QWORD *)v81;
          }
        }
        v48 = *((_QWORD *)a2 + 423);
        v24 = *(_QWORD *)(v48 + 848);
        if ( *(_QWORD *)(v24 + 8)
          || *(_QWORD *)(v24 + 16)
          || *(int *)v24 < 0
          || *(_WORD *)(*(_QWORD *)(v48 + 856) + 4LL) > v38 )
        {
          MsScrubContextCaptureError(v48, v24);
        }
LABEL_105:
        v26 = v81;
LABEL_106:
        if ( v79 )
        {
          HasGlobalBindingSemantics = CmsBPlusTable::HasGlobalBindingSemantics(v86);
          for ( j = v86; *((CmsBPlusTable **)j + 8) != j; j = (CmsBPlusTable *)*((_QWORD *)j + 8) )
            ;
          MspAddDirtyPageCount(v32, *((struct SmsBindable **)j + 9), v83, HasGlobalBindingSemantics);
        }
        goto LABEL_136;
      }
    }
    else
    {
      if ( _bittest64((const signed __int64 *)a2, 0x38u) )
      {
        v22 = -1073741608;
        goto LABEL_114;
      }
      IsPageStateNew = SmsPage::IsPageStateNew(v81);
      v32 = v85;
      Page = CmsVolume::ReadPage(v85, a2, v86, v81, 0, 1, IsPageStateNew);
      v22 = Page;
      if ( Page >= 0 )
      {
        v22 = 0;
        goto LABEL_105;
      }
    }
    v26 = v81;
LABEL_115:
    if ( !v79 )
      goto LABEL_118;
    *((_QWORD *)v26 + 42) = 0;
    _InterlockedAnd((volatile signed __int32 *)v81 + 138, 0xFFFFFF7F);
LABEL_117:
    v26 = v81;
LABEL_118:
    if ( v80 && v26 )
    {
      v53 = v85;
      v54 = (v27 != 0) + 2;
      while ( 1 )
      {
        v55 = 0;
        v56 = v54;
        if ( *((_QWORD *)v26 + 38) )
        {
          if ( (v54 & 1) != 0 )
          {
            v57 = (_DWORD *)((char *)v26 + 312);
            if ( *((_DWORD *)v26 + 96) == *((_DWORD *)v26 + 78) )
            {
              v58 = (int *)((char *)v26 + 316);
              v55 = (SmsPage *)*((_QWORD *)v26 + 38);
              if ( (v54 & 4) == 0 )
                goto LABEL_131;
              v59 = *v58;
              if ( *((_DWORD *)v26 + 97) != *v58 )
              {
                v56 = v54 & 0xFFFFFFFB;
                goto LABEL_131;
              }
LABEL_130:
              *v58 = v59 - 1;
LABEL_131:
              v60 = (*v57)-- == 1;
              if ( v60 )
                *((_QWORD *)v26 + 38) = 0;
              goto LABEL_133;
            }
          }
          if ( (v54 & 4) != 0 )
          {
            v58 = (int *)((char *)v26 + 316);
            v59 = *((_DWORD *)v26 + 79);
            if ( *((_DWORD *)v26 + 97) == v59 )
            {
              v57 = (_DWORD *)((char *)v26 + 312);
              v55 = (SmsPage *)*((_QWORD *)v26 + 38);
              goto LABEL_130;
            }
          }
        }
LABEL_133:
        CmsVolume::UnpinInternal(v53, a2, v26, v54);
        v26 = v55;
        v54 = v56;
        if ( !v55 )
        {
          v22 = Page;
          break;
        }
      }
    }
LABEL_135:
    v81 = 0;
    v26 = 0;
LABEL_136:
    if ( !v78 )
      break;
    HIWORD(v61) = HIWORD(v84);
    LOWORD(v61) = v84 + 1;
    v9 = v90;
    v84 = v61;
    if ( (unsigned __int16)v61 > (unsigned __int8)word_140269174 )
      MsDelayExecutionThread(0);
  }
  v18 = v91;
  if ( v22 < 0 )
  {
    CmsBPlusTable::FreeUndoRecord(Undo, (struct CmsTransactionContext *)v24, v25);
    goto LABEL_151;
  }
  v62 = Undo;
  v63 = (void *)*((_QWORD *)Undo + 3);
  SmsMultiPageUndoRecord::PinPages(v63, a2, v26, 1, 0, 0);
  CmsBPlusTable::FormatUndoRecord(v86, a2, v62, 0, v63, 0x20u, 0);
  v64 = v96;
  RtlCopyMemoryNonTemporal(
    (void *)(*((_QWORD *)v26 + 13) + 80LL),
    (const void *)(*((_QWORD *)v96 + 13) + 80LL),
    *((unsigned int *)v96 + 80) - 80LL);
  *((_QWORD *)v26 + 32) = v64;
  v60 = *((_QWORD *)v64 + 83) == 0;
  *((_QWORD *)v64 + 33) = v26;
  if ( !v60 && *((_BYTE *)v64 + 392) != 0xF8 )
  {
    if ( byte_140269188 )
    {
      ++dword_140268F0C;
      if ( (unsigned __int8)ExTryAcquireAutoExpandPushLockExclusive(
                              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v64 + 12) + 32LL) + 40LL),
                              2) )
      {
        v65 = (CmsCachedPin *)*((_QWORD *)v64 + 83);
        if ( v65 && (*((_DWORD *)v65 + 26) & 1) != 0 && !CmsCachedPin::ShouldDoomCachedPin(v65) )
        {
          *((_QWORD *)v26 + 83) = v66;
          *((_QWORD *)v64 + 83) = 0;
          v67 = *((_QWORD *)v26 + 83);
          v95 = v64;
          v94 = v26;
          *(_QWORD *)(v67 + 32) = v26;
          *(_DWORD *)(*((_QWORD *)v26 + 83) + 88LL) = *((_DWORD *)v26 + 92);
          *((_DWORD *)v26 + 93) = *((_DWORD *)v64 + 93) + 1;
          *(_QWORD *)(*((_QWORD *)v26 + 83) + 120LL) = *((_QWORD *)v26 + 13)
                                                     + 80LL
                                                     + *(unsigned int *)(*((_QWORD *)v26 + 13) + 80LL);
          ++dword_140268F10;
          ++*(_DWORD *)(*((_QWORD *)v26 + 83) + 148LL);
        }
        ExReleaseAutoExpandPushLockExclusive(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v64 + 12) + 32LL) + 40LL), 2);
      }
    }
  }
  ++*((_DWORD *)v64 + 92);
  SmsPage::UpdatePersistentQIsForPageCow(v64, a2, v26);
  v68 = (void *)*((_QWORD *)v18 + 3);
  SmsMultiPageUndoRecord::PinPages(v68, a2, v64, 4, v26, 1);
  CmsBPlusTable::FormatUndoRecord(*((CmsBPlusTable **)v64 + 12), a2, v18, 0, v68, 0x20u, 0);
LABEL_152:
  if ( v94 )
    SmsPage::Repin(v94, a2, 1);
  v69 = v95;
  if ( v95 )
  {
    v70 = 2;
    v71 = *(CmsVolume **)(*(_QWORD *)(*((_QWORD *)v95 + 12) + 112LL) + 16LL);
    do
    {
      v72 = 0;
      v73 = v70;
      if ( *((_QWORD *)v69 + 38) )
      {
        if ( (v70 & 1) != 0 )
        {
          v74 = (_DWORD *)((char *)v69 + 312);
          if ( *((_DWORD *)v69 + 96) == *((_DWORD *)v69 + 78) )
          {
            v75 = (int *)((char *)v69 + 316);
            v72 = (struct SmsPage *)*((_QWORD *)v69 + 38);
            if ( (v70 & 4) == 0 )
              goto LABEL_166;
            v76 = *v75;
            if ( *((_DWORD *)v69 + 97) != *v75 )
            {
              v73 = v70 & 0xFFFFFFFB;
              goto LABEL_166;
            }
LABEL_165:
            *v75 = v76 - 1;
LABEL_166:
            v60 = (*v74)-- == 1;
            if ( v60 )
              *((_QWORD *)v69 + 38) = 0;
            goto LABEL_168;
          }
        }
        if ( (v70 & 4) != 0 )
        {
          v75 = (int *)((char *)v69 + 316);
          v76 = *((_DWORD *)v69 + 79);
          if ( *((_DWORD *)v69 + 97) == v76 )
          {
            v74 = (_DWORD *)((char *)v69 + 312);
            v72 = (struct SmsPage *)*((_QWORD *)v69 + 38);
            goto LABEL_165;
          }
        }
      }
LABEL_168:
      CmsVolume::UnpinInternal(v71, a2, v69, v70);
      v69 = v72;
      v70 = v73;
    }
    while ( v72 );
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x14006ec00  push    rbp
0x14006ec02  push    rbx
0x14006ec03  push    rsi
0x14006ec04  push    rdi
0x14006ec05  push    r12
0x14006ec07  push    r13
0x14006ec09  push    r14
0x14006ec0b  push    r15
0x14006ec0d  lea     rbp, [rsp-38h]
0x14006ec12  sub     rsp, 138h
0x14006ec19  mov     rax, cs:__security_cookie
0x14006ec20  xor     rax, rsp
0x14006ec23  mov     [rbp+70h+var_50], rax
0x14006ec27  mov     rdi, [r9+60h]
0x14006ec2b  mov     r15, rdx
0x14006ec2e  mov     al, [r9+188h]
0x14006ec35  mov     rdx, rcx
0x14006ec38  mov     [rbp+70h+var_D8], 0
0x14006ec40  mov     rsi, r9
0x14006ec43  mov     [rbp+70h+var_E8], rdi
0x14006ec47  mov     r13, r8
0x14006ec4a  mov     rcx, [r15]
0x14006ec4d  mov     [rbp+70h+var_E0], 0
0x14006ec55  mov     [rbp+70h+var_D0], al
0x14006ec58  mov     rax, [rdi+0A0h]
0x14006ec5f  mov     [rbp+70h+var_98], r9
0x14006ec63  mov     [rbp+70h+var_C8], r8
0x14006ec67  mov     [rbp+70h+var_D8], rax
0x14006ec6b  bt      rcx, 0Bh
0x14006ec70  jnb     short loc_14006EC84
0x14006ec72  bt      rcx, 9
0x14006ec77  jb      short loc_14006EC84
0x14006ec79  mov     rax, [rdi+0A8h]
0x14006ec80  mov     [rbp+70h+var_D8], rax
0x14006ec84  xor     eax, eax
0x14006ec86  xor     r8d, r8d
0x14006ec89  mov     [rbp+70h+var_A0], rax
0x14006ec8d  mov     [rbp+70h+var_A8], r8
0x14006ec91  lea     r12d, [rax+1]
0x14006ec95  bt      rcx, 0Ch
0x14006ec9a  jnb     short loc_14006ECBF
0x14006ec9c  mov     rax, cs:KdDebuggerEnabled
0x14006eca3  cmp     [rax], r8b
0x14006eca6  jz      short loc_14006ECA9
0x14006eca8  int     3; Trap to Debugger
0x14006eca9  mov     rcx, [r15+8]
0x14006ecad  mov     r8b, r12b
0x14006ecb0  mov     edx, 20000000h
0x14006ecb5  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x14006ecba  jmp     loc_14006EDA3
0x14006ecbf  mov     rax, [rdx+1C8h]
0x14006ecc6  xor     ecx, ecx; ProcNumber
0x14006ecc8  mov     [rbp+70h+var_F0], rax
0x14006eccc  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14006ecd3  nop     dword ptr [rax+rax+00h]
0x14006ecd8  xor     edx, edx; struct std::nothrow_t *
0x14006ecda  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14006ece0  lea     rbx, [rdx+rdx*2]
0x14006ece4  shl     rbx, 6
0x14006ece8  add     rbx, cs:qword_140269410
0x14006ecef  cmp     dword ptr [rbx], 78h ; 'x'
0x14006ecf2  jb      short loc_14006ED73
0x14006ecf4  cmp     byte ptr [rbx+8], 0
0x14006ecf8  jz      short loc_14006ED23
0x14006ecfa  cmp     byte ptr [rbx+9], 0
0x14006ecfe  lea     rcx, [rbx+40h]; Lookaside
0x14006ed02  jz      short loc_14006ED12
0x14006ed04  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006ed0b  nop     dword ptr [rax+rax+00h]
0x14006ed10  jmp     short loc_14006ED1E
0x14006ed12  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14006ed19  nop     dword ptr [rax+rax+00h]
0x14006ed1e  mov     r14, rax
0x14006ed21  jmp     short loc_14006ED64
0x14006ed23  mov     rax, [rbx+58h]
0x14006ed27  mov     rcx, rax
0x14006ed2a  shr     rcx, 20h
0x14006ed2e  cmp     eax, ecx
0x14006ed30  jle     short loc_14006ED69
0x14006ed32  nop
0x14006ed33  or      ecx, 0FFFFFFFFh
0x14006ed36  lock xadd [rbx+58h], ecx
0x14006ed3b  nop
0x14006ed3c  dec     ecx
0x14006ed3e  mov     eax, [rbx+5Ch]
0x14006ed41  cmp     ecx, eax
0x14006ed43  jl      short loc_14006ED5B
0x14006ed45  test    ecx, ecx
0x14006ed47  js      short loc_14006ED5B
0x14006ed49  lea     rcx, [rbx+40h]; ListHead
0x14006ed4d  call    cs:__imp_ExpInterlockedPopEntrySList
0x14006ed54  nop     dword ptr [rax+rax+00h]
0x14006ed59  jmp     short loc_14006ED1E
0x14006ed5b  xor     r14d, r14d
0x14006ed5e  nop
0x14006ed5f  lock inc dword ptr [rbx+58h]
0x14006ed63  nop
0x14006ed64  test    r14, r14
0x14006ed67  jnz     short loc_14006ED93
0x14006ed69  test    rbx, rbx
0x14006ed6c  jz      short loc_14006ED75
0x14006ed6e  mov     ecx, [rbx+4]
0x14006ed71  jmp     short loc_14006ED7A
0x14006ed73  xor     ebx, ebx
0x14006ed75  mov     ecx, 88h; unsigned __int64
0x14006ed7a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14006ed7f  mov     [rbp+70h+var_C0], rax
0x14006ed83  mov     r14, rax
0x14006ed86  test    al, 0Fh
0x14006ed88  jnz     loc_14006F7EB
0x14006ed8e  test    rax, rax
0x14006ed91  jz      short loc_14006ED9E
0x14006ed93  mov     [r14], rbx
0x14006ed96  add     r14, 10h
0x14006ed9a  mov     [rbp+70h+var_C0], r14
0x14006ed9e  test    r14, r14
0x14006eda1  jnz     short loc_14006EDB0
0x14006eda3  xor     r14d, r14d
0x14006eda6  mov     esi, 0C000009Ah
0x14006edab  jmp     loc_14006F6EE
0x14006edb0  mov     [r14+10h], r12d
0x14006edb4  mov     ecx, 20h ; ' '
0x14006edb9  mov     [r14+0Ch], ecx
0x14006edbd  xorps   xmm0, xmm0
0x14006edc0  mov     [r14+8], ecx
0x14006edc4  xor     eax, eax
0x14006edc6  mov     [r14+28h], rdi
0x14006edca  mov     rdx, r15
0x14006edcd  mov     word ptr [r14+14h], 0
0x14006edd4  lea     r8d, [rcx-13h]
0x14006edd8  movups  xmmword ptr [r14+30h], xmm0
0x14006eddd  mov     dword ptr [rsp+170h+var_148], 0
0x14006ede5  movups  xmmword ptr [r14+40h], xmm0
0x14006edea  mov     [r14+50h], rax
0x14006edee  lea     rax, [r14+58h]
0x14006edf2  mov     [r14+18h], rax
0x14006edf6  mov     dword ptr [r14+20h], 0
0x14006edfe  movups  xmmword ptr [rax], xmm0
0x14006ee01  mov     dword ptr [rsp+170h+Timeout], ecx
0x14006ee05  movups  xmmword ptr [rax+10h], xmm0
0x14006ee09  mov     eax, [rsi+178h]
0x14006ee0f  mov     rcx, [rbp+70h+var_E8]
0x14006ee13  mov     [rsp+170h+var_F8], eax
0x14006ee17  call    ?AllocateUndo@CmsBPlusTable@@QEAAPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@W4_MS_UNDO_OPERATION@@EKJKE@Z; CmsBPlusTable::AllocateUndo(CmsTransactionContext *,_MS_UNDO_OPERATION,uchar,ulong,long,ulong,uchar)
0x14006ee1c  mov     [rbp+70h+var_B0], rax
0x14006ee20  test    rax, rax
0x14006ee23  jz      short loc_14006EDA6
0x14006ee25  mov     [rsp+170h+var_F4], 0
0x14006ee2d  mov     r14d, 2
0x14006ee33  xor     r8d, r8d; State
0x14006ee36  mov     [rsp+170h+var_108], 0
0x14006ee3f  xor     edx, edx; Type
0x14006ee41  mov     [rbp+70h+var_B8], 0
0x14006ee49  lea     rcx, [rbp+70h+Event.Header.WaitListHead]; Event
0x14006ee4d  mov     qword ptr [rbp+70h+Event.Header], 0
0x14006ee55  call    cs:__imp_KeInitializeEvent
0x14006ee5c  nop     dword ptr [rax+rax+00h]
0x14006ee61  mov     rbx, [rbp+70h+var_F0]
0x14006ee65  lea     rax, [rsp+170h+var_108]
0x14006ee6a  mov     r8, [rbp+70h+var_E8]; struct CmsBPlusTable *
0x14006ee6e  mov     r9, r13; union _LCN_TUPLE *
0x14006ee71  mov     [rsp+170h+var_148], rax; struct SmsPage **
0x14006ee76  mov     rdx, r15; struct CmsTransactionContext *
0x14006ee79  lea     rax, [rbp+70h+Event]
0x14006ee7d  mov     rcx, rbx; this
0x14006ee80  mov     [rsp+170h+Timeout], rax; struct SmsWaitListEntry *
0x14006ee85  call    ?LookupPageTableEntry@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEBT_LCN_TUPLE@@PEAUSmsWaitListEntry@@PEAPEAUSmsPage@@@Z; CmsVolume::LookupPageTableEntry(CmsTransactionContext *,CmsBPlusTable *,_LCN_TUPLE const *,SmsWaitListEntry *,SmsPage * *)
0x14006ee8a  mov     esi, eax
0x14006ee8c  cmp     eax, 0C0000804h
0x14006ee91  jnz     short loc_14006EEBE
0x14006ee93  xor     r9d, r9d; Alertable
0x14006ee96  mov     [rsp+170h+Timeout], 0; Timeout
0x14006ee9f  xor     r8d, r8d; WaitMode
0x14006eea2  lea     rcx, [rbp+70h+Event.Header.WaitListHead]; Object
0x14006eea6  xor     edx, edx; WaitReason
0x14006eea8  call    cs:__imp_KeWaitForSingleObject
0x14006eeaf  nop     dword ptr [rax+rax+00h]
0x14006eeb4  mov     [rsp+170h+var_110], r12b
0x14006eeb9  jmp     loc_14006F49B
0x14006eebe  mov     rdi, [rsp+170h+var_108]
0x14006eec3  xor     esi, esi
0x14006eec5  mov     [rsp+170h+var_10F], sil
0x14006eeca  mov     r13b, sil
0x14006eecd  mov     [rsp+170h+var_110], sil
0x14006eed2  test    rdi, rdi
0x14006eed5  jnz     loc_14006EF74
0x14006eedb  test    dword ptr [rbx+0D44h], 20000000h
0x14006eee5  jz      short loc_14006EEF1
0x14006eee7  mov     esi, 0C000026Eh
0x14006eeec  jmp     loc_14006F49B
0x14006eef1  mov     rcx, [rbp+70h+var_E8]; this
0x14006eef5  xor     r8d, r8d; bool
0x14006eef8  xor     edx, edx; bool
0x14006eefa  call    ?AreWritesDoomed@CmsBPlusTable@@QEAAE_N0@Z; CmsBPlusTable::AreWritesDoomed(bool,bool)
0x14006eeff  test    al, al
0x14006ef01  jz      short loc_14006EF0D
0x14006ef03  mov     esi, 0C0000001h
0x14006ef08  jmp     loc_14006F49B
0x14006ef0d  mov     r9, [rbp+70h+var_C8]; union _LCN_TUPLE *
0x14006ef11  lea     rax, [rbp+70h+var_B8]
0x14006ef15  mov     [rsp+170h+var_138], rax; struct SmsPage **
0x14006ef1a  lea     r8, [rbp+70h+var_E8]; struct SmsView *
0x14006ef1e  mov     eax, [rsp+170h+var_F8]
0x14006ef22  mov     rdx, r15; struct CmsTransactionContext *
0x14006ef25  mov     byte ptr [rsp+170h+var_140], r12b; unsigned __int8
0x14006ef2a  mov     rcx, rbx; this
0x14006ef2d  mov     byte ptr [rsp+170h+var_148], r12b; unsigned __int8
0x14006ef32  mov     dword ptr [rsp+170h+Timeout], eax; unsigned int
0x14006ef36  call    ?InsertNewPageTableEntry@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAUSmsView@@PEBT_LCN_TUPLE@@KEEPEAPEAUSmsPage@@@Z; CmsVolume::InsertNewPageTableEntry(CmsTransactionContext *,SmsView *,_LCN_TUPLE const *,ulong,uchar,uchar,SmsPage * *)
0x14006ef3b  mov     [rsp+170h+var_100], eax
0x14006ef3f  mov     esi, eax
0x14006ef41  cmp     eax, 0C0000035h
0x14006ef46  jnz     short loc_14006EF58
0x14006ef48  mov     esi, 0C0000804h
0x14006ef4d  mov     [rsp+170h+var_110], r12b
0x14006ef52  mov     [rsp+170h+var_100], esi
0x14006ef56  jmp     short loc_14006EFBA
0x14006ef58  test    eax, eax
0x14006ef5a  js      short loc_14006EFB5
0x14006ef5c  mov     rdi, [rbp+70h+var_B8]
0x14006ef60  xor     esi, esi
0x14006ef62  mov     [rsp+170h+var_108], rdi
0x14006ef67  mov     r13b, r12b
0x14006ef6a  mov     [rsp+170h+var_110], sil
0x14006ef6f  mov     [rsp+170h+var_10F], r12b
0x14006ef74  mov     [rsp+170h+var_10E], r12b
0x14006ef79  mov     al, [rbp+70h+var_D0]
0x14006ef7c  cmp     [rdi+188h], al
0x14006ef82  jnz     loc_14006F3A6
0x14006ef88  test    r13b, r13b
0x14006ef8b  jnz     short loc_14006EFCE
0x14006ef8d  xor     r9d, r9d; bool
0x14006ef90  mov     r8b, r12b; bool
0x14006ef93  mov     rdx, r15; struct CmsTransactionContext *
0x14006ef96  mov     rcx, rdi; this
0x14006ef99  call    ?AcquirePageLock@SmsPage@@QEAAJPEAVCmsTransactionContext@@_N1@Z; SmsPage::AcquirePageLock(CmsTransactionContext *,bool,bool)
0x14006ef9e  mov     [rsp+170h+var_100], eax
0x14006efa2  mov     esi, eax
0x14006efa4  test    eax, eax
0x14006efa6  jns     short loc_14006EFC4
0x14006efa8  nop
0x14006efa9  lock inc cs:dword_140269560
0x14006efb0  jmp     loc_14006F3D2
0x14006efb5  mov     [rsp+170h+var_110], r13b
0x14006efba  mov     [rsp+170h+var_10E], r13b
0x14006efbf  jmp     loc_14006F3D3
0x14006efc4  mov     rdi, [rsp+170h+var_108]
0x14006efc9  mov     r13b, r12b
0x14006efcc  xor     esi, esi
0x14006efce  mov     rax, [r15]
0x14006efd1  test    r14b, al
0x14006efd4  jnz     short loc_14006F014
0x14006efd6  bt      rax, 0Ch
0x14006efdb  jb      short loc_14006F014
0x14006efdd  test    dword ptr [rbx+0D44h], 20000000h
0x14006efe7  jz      short loc_14006EFF3
0x14006efe9  mov     esi, 0C000026Eh
0x14006efee  jmp     loc_14006F3AB
0x14006eff3  mov     rcx, [rbp+70h+var_E8]; this
0x14006eff7  xor     r8d, r8d; bool
0x14006effa  xor     edx, edx; bool
0x14006effc  call    ?AreWritesDoomed@CmsBPlusTable@@QEAAE_N0@Z; CmsBPlusTable::AreWritesDoomed(bool,bool)
0x14006f001  mov     rdi, [rsp+170h+var_108]
0x14006f006  test    al, al
0x14006f008  jz      short loc_14006F014
0x14006f00a  mov     esi, 0C0000001h
0x14006f00f  jmp     loc_14006F3AB
0x14006f014  mov     rcx, [rbp+70h+var_E0]
0x14006f018  movzx   ebx, sil
0x14006f01c  test    rcx, rcx
0x14006f01f  jz      short loc_14006F02F
0x14006f021  mov     rax, [rdi+160h]
0x14006f028  cmp     [rcx], rax
0x14006f02b  cmovb   ebx, r12d
0x14006f02f  mov     eax, [r15]
0x14006f032  bt      rax, 0Bh
0x14006f037  jb      short loc_14006F054
0x14006f039  mov     rcx, rdi; this
0x14006f03c  call    ?IsPageStateMapped@SmsPage@@QEBA_NXZ; SmsPage::IsPageStateMapped(void)
0x14006f041  test    al, al
0x14006f043  jz      short loc_14006F04F
0x14006f045  mov     rcx, [rsp+170h+var_108]; this
0x14006f04a  call    ?IsPageStateResident@SmsPage@@QEBA_NXZ; SmsPage::IsPageStateResident(void)
0x14006f04f  mov     rdi, [rsp+170h+var_108]
0x14006f054  test    bl, bl
0x14006f056  jnz     loc_14006F3A6
0x14006f05c  lea     rdx, [rbp+70h+var_E8]; struct SmsView *
0x14006f060  mov     rcx, rdi; this
0x14006f063  call    ?IsDeleted@SmsPage@@QEAAEPEBUSmsView@@@Z; SmsPage::IsDeleted(SmsView const *)
0x14006f068  test    al, al
0x14006f06a  jnz     loc_14006F3A1
0x14006f070  mov     rcx, [rsp+170h+var_108]; this
0x14006f075  call    ?IsPageStateAbandoned@SmsPage@@QEBA_NXZ; SmsPage::IsPageStateAbandoned(void)
0x14006f07a  mov     rdi, [rsp+170h+var_108]
0x14006f07f  test    al, al
0x14006f081  jz      short loc_14006F08D
0x14006f083  mov     [rsp+170h+var_110], r12b
0x14006f088  jmp     loc_14006F3A6
0x14006f08d  mov     eax, [rdi+228h]
0x14006f093  test    al, 4
  ... truncated ...
```
