# CmsTxMemLog::AddRedoRecord(CmsBPlusTable *,_MS_REDO_OPERATION,_CmsKey const *,_CmsData const *,_CmsData const *,ulong,CmsBPlusTable *,_EMS_REDO_FLAGS,uchar,long *)

- ea: `0x14007d820`
- end: `0x14007e098`
- name: `?AddRedoRecord@CmsTxMemLog@@QEAAJPEAVCmsBPlusTable@@W4_MS_REDO_OPERATION@@PEBU_CmsKey@@PEBU_CmsData@@3K0W4_EMS_REDO_FLAGS@@EPEAJ@Z`
- size: `2168`
- prototype: ``
- caller_count: `17`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001be70`
- `0x14002e228`
- `0x14003ca00`
- `0x14003f39c`
- `0x14003f780`
- `0x1400404d0`
- `0x140040610`
- `0x1400411cc`
- `0x140041320`
- `0x140062700`
- `0x140091570`
- `0x140093480`
- `0x140093d50`
- `0x140094a0c`
- `0x1400c0ec0`
- `0x1400c7dfc`
- `0x1400d26a0`

## callees

- `0x140022ba8`
- `0x14007d820`
- `0x14007e0a0`
- `0x14007e6bc`
- `0x14008bd30`
- `0x14008c9a0`
- `0x1400902a0`
- `0x1400ceda0`
- `0x14015761c`
- `0x1401578b0`
- `0x14015f294`
- `0x14017cc0c`
- `0x1401f3fc0`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x140200355`
- `ntoskrnl!IoGetActivityIdThread` at `0x140200355`
- `ntoskrnl!KeSetEvent` at `0x14007e009`
- `ntoskrnl!KeSetEvent` at `0x14007e009`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007dcce`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007dcce`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007dfaa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007dfaa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007da27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007da27`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007da8e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007da8e`
- `ntoskrnl!ExAllocatePool2` at `0x14007db99`
- `ntoskrnl!ExAllocatePool2` at `0x14007dc0e`
- `ntoskrnl!ExAllocatePool2` at `0x14007db99`
- `ntoskrnl!ExAllocatePool2` at `0x14007dc0e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007dbd1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007dbd1`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200308`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140200308`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007db63`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007db63`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14020039a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14020039a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007dfc7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14007dfc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dc96`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dcdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e03b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dc96`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dcdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007e03b`

## string_xrefs

- `0x14007dc1e`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsTxMemLog::AddRedoRecord(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        _DWORD *a4,
        _DWORD *a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        char a10,
        volatile signed __int32 *a11)
{
  __int64 v12; // r11
  __int64 v13; // r12
  _DWORD *v14; // r10
  __int64 v15; // rax
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rax
  _DWORD *v19; // rcx
  __int64 v20; // r15
  int v21; // edi
  unsigned int v22; // ebx
  __int64 v23; // rdx
  __int64 v24; // r8
  struct _SmsRedoBlock *v25; // r13
  unsigned int v26; // ebx
  __int64 v27; // rcx
  __int64 v28; // r14
  char v29; // di
  __int64 v30; // rcx
  unsigned int v31; // esi
  __int64 v32; // r12
  __int64 v33; // rbx
  KSPIN_LOCK *v34; // rdi
  KIRQL v35; // al
  __int64 v36; // r10
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned int v39; // r11d
  unsigned __int64 v40; // rbx
  unsigned __int64 v41; // rbx
  __int64 v42; // r8
  __int64 v43; // rbx
  struct _SLIST_ENTRY *v44; // r8
  struct _NPAGED_LOOKASIDE_LIST *v45; // rcx
  struct _SmsRedoBlock *Pool2; // rax
  __int64 EntryHeaderSize; // rdi
  __int64 v48; // rbx
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // rax
  bool v52; // zf
  __int64 v53; // rax
  __int64 v54; // rdx
  int v56; // ecx
  _QWORD *v57; // r9
  unsigned __int8 v58; // r8
  unsigned int v59; // edi
  __int64 v60; // rcx
  int v61; // r10d
  __int16 v62; // dx
  __int64 v63; // r11
  __int64 v64; // r8
  __int64 v65; // rax
  unsigned int v66; // ecx
  __int64 v67; // rax
  __int128 v68; // xmm1
  __int64 v69; // rdx
  int *v70; // rax
  __int64 v71; // rax
  __int64 LogMetadataAddress; // rax
  int v73; // ecx
  int v74; // eax
  struct _SmsRedoBlock *PreallocatedRedo; // rax
  struct _NPAGED_LOOKASIDE_LIST *v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // r14
  __int64 v79; // rsi
  __int64 v80; // rdi
  char LogFullPercentage; // bl
  __int64 v82; // rdx
  __int64 v83; // rcx
  int ActivityIdThread; // eax
  char v85; // [rsp+60h] [rbp-A0h]
  char v86; // [rsp+61h] [rbp-9Fh]
  char v87; // [rsp+62h] [rbp-9Eh]
  unsigned int v88; // [rsp+64h] [rbp-9Ch]
  unsigned __int64 v90; // [rsp+70h] [rbp-90h]
  struct _SmsRedoBlock **v92; // [rsp+90h] [rbp-70h] BYREF
  volatile signed __int32 *v93; // [rsp+98h] [rbp-68h]
  _QWORD *v94; // [rsp+A0h] [rbp-60h]
  __int64 v95; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v96; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v97; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v98; // [rsp+C0h] [rbp-40h]
  __int128 v99; // [rsp+D0h] [rbp-30h]
  int v100; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v101; // [rsp+E4h] [rbp-1Ch]
  __int16 v102; // [rsp+E6h] [rbp-1Ah]
  __int64 v103; // [rsp+E8h] [rbp-18h]
  _QWORD v104[10]; // [rsp+F0h] [rbp-10h]
  unsigned __int8 v105; // [rsp+140h] [rbp+40h]

  v12 = a6;
  v13 = a1;
  v93 = a11;
  v14 = a4;
  v15 = a2[3];
  v16 = a8;
  v94 = a2;
  v17 = a2[14];
  v18 = *(_QWORD *)(v15 + 72);
  v97 = a1;
  v19 = a5;
  v20 = v18 + 2816;
  v95 = v17;
  v96 = v18;
  v87 = 0;
  if ( a2 == *(_QWORD **)(v13 + 40) )
  {
    v85 = 1;
    v21 = 0;
    v22 = 56;
  }
  else
  {
    v57 = a2;
    v105 = *(_BYTE *)(v17 + 8) + 1;
    v58 = v105;
    v59 = v105 - 1;
    if ( v105 == 1 )
    {
      v85 = 0;
      v22 = 56;
    }
    else
    {
      do
      {
        v22 = 56;
        v85 = 0;
        v60 = *(_QWORD *)(v57[14] + 32LL);
        v61 = *(_DWORD *)(v60 + 8);
        v62 = *(_WORD *)(v60 + 12);
        v63 = *(_QWORD *)(v60 + 16);
        v64 = *(_QWORD *)(*(_QWORD *)v60 + 24LL);
        if ( (*(_DWORD *)(v64 + 44) & 1) != 0 )
        {
          v61 -= 8;
          v62 &= ~4u;
          v63 += 8;
        }
        WORD3(v98) = *(_WORD *)(v60 + 14);
        *(_QWORD *)&v99 = *(unsigned int *)(v64 + 16);
        v65 = v57[3];
        LODWORD(v98) = v61;
        WORD2(v98) = v62;
        *((_QWORD *)&v98 + 1) = v63;
        v66 = *(_DWORD *)(v65 + 16);
        v67 = 4LL * v59;
        *((_QWORD *)&v99 + 1) = v66;
        v68 = v99;
        *(_OWORD *)((char *)&v100 + v67 * 8) = v98;
        *(_OWORD *)&v104[v67] = v68;
        v57 = **(_QWORD ***)(v57[14] + 32LL);
        --v59;
      }
      while ( v59 );
      v58 = v105;
      v14 = a4;
      v12 = a6;
    }
    v21 = 0;
    v69 = v57[9] + 376LL;
    v104[1] = *(unsigned int *)(v57[3] + 16LL);
    v102 = WORD3(v98);
    v70 = &v100;
    v100 = 16;
    v101 = 0;
    v103 = v69;
    v104[0] = 57392;
    while ( v70 != &v100 + 8 * v58 )
    {
      v21 += ((*v70 + 23) & 0xFFFFFFF8) + 8;
      v70 += 8;
    }
    v19 = a5;
    v16 = a8;
  }
  if ( v14 )
    v22 = ((*v14 + 7) & 0xFFFFFFF8) + 64;
  if ( v19 )
    v22 += ((*v19 + 7) & 0xFFFFFFF8) + 8;
  v23 = 0;
  v24 = 0;
  if ( v12 )
    v23 = a7;
  if ( (_DWORD)v23 )
  {
    do
    {
      v71 = 2LL * (unsigned int)v24;
      v24 = (unsigned int)(v24 + 1);
      v22 += ((*(_DWORD *)(v12 + 8 * v71) + 7) & 0xFFFFFFF8) + 8;
    }
    while ( (unsigned int)v24 < (unsigned int)v23 );
  }
  if ( v16 )
  {
    v74 = CanonicalKeyLength(v16, v23, v24);
    v14 = a4;
    v16 = a8;
    v12 = a6;
    v22 += ((v74 + 15) & 0xFFFFFFF8) + 8;
  }
  v25 = *(struct _SmsRedoBlock **)(v13 + 32);
  v26 = (v21 + v22 + 7) & 0xFFFFFFF8;
  v88 = v26;
  if ( v25 && (v27 = *((unsigned int *)v25 + 7), *((_DWORD *)v25 + 6) - (int)v27 > v26) )
  {
    v28 = v27 + *((_QWORD *)v25 + 1);
    v29 = 1;
    v86 = 1;
    *(_OWORD *)v28 = 0;
    *(_OWORD *)(v28 + 16) = 0;
    *(_OWORD *)(v28 + 32) = 0;
    *(_QWORD *)(v28 + 48) = 0;
  }
  else
  {
    v29 = 0;
    v86 = 0;
    if ( !a10 )
      goto LABEL_39;
    v92 = 0;
    PreallocatedRedo = FindPreallocatedRedo((struct _SmsRedoBlock **)(v13 + 16), v26, &v92);
    v25 = PreallocatedRedo;
    if ( !PreallocatedRedo )
      goto LABEL_39;
    v14 = a4;
    v16 = a8;
    v12 = a6;
    *v92 = (struct _SmsRedoBlock *)*((_QWORD *)PreallocatedRedo + 6);
    v28 = *((_QWORD *)PreallocatedRedo + 2);
    *((_QWORD *)PreallocatedRedo + 6) = 0;
    v87 = 1;
  }
  if ( v28 )
    goto LABEL_17;
LABEL_39:
  Pool2 = (struct _SmsRedoBlock *)ExAllocatePool2(66, 72, 1766871885, v16);
  v25 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, 0x48u);
  EntryHeaderSize = (unsigned int)LogGetEntryHeaderSize(*(_QWORD *)(v20 + 72), v26 + 8);
  v48 = qword_140269440 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  if ( (unsigned int)EntryHeaderSize > *(_DWORD *)v48 )
  {
    v48 = 0;
    v50 = EntryHeaderSize + 16;
    goto LABEL_42;
  }
  if ( *(_BYTE *)(v48 + 8) )
  {
    v76 = (struct _NPAGED_LOOKASIDE_LIST *)(v48 + 64);
    if ( *(_BYTE *)(v48 + 9) )
      v51 = (__int64)ExAllocateFromNPagedLookasideList(v76);
    else
      v51 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v76);
LABEL_77:
    if ( v51 )
      goto LABEL_78;
    goto LABEL_65;
  }
  if ( (int)*(_QWORD *)(v48 + 88) > (int)HIDWORD(*(_QWORD *)(v48 + 88)) )
  {
    v56 = _InterlockedDecrement((volatile signed __int32 *)(v48 + 88));
    if ( v56 >= *(_DWORD *)(v48 + 92) && v56 >= 0 )
    {
      v51 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v48 + 64));
      goto LABEL_77;
    }
    _InterlockedIncrement((volatile signed __int32 *)(v48 + 88));
  }
LABEL_65:
  v50 = *(unsigned int *)(v48 + 4);
LABEL_42:
  v51 = ExAllocatePool2(66, v50, 1766871885, v49);
  if ( (v51 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( !v51 )
    goto LABEL_57;
LABEL_78:
  *(_QWORD *)v51 = v48;
  if ( v51 == -16 )
  {
LABEL_57:
    ExFreePoolWithTag(v25, 0);
    return 3221225626LL;
  }
  *(_QWORD *)v25 = v51 + 16;
  LogMetadataAddress = MlLogGetLogMetadataAddress(*(_QWORD *)(v20 + 72));
  *((_QWORD *)v25 + 1) = LogMetadataAddress;
  LogMetadataAddress += 8;
  *((_QWORD *)v25 + 2) = LogMetadataAddress;
  *(_OWORD *)LogMetadataAddress = 0;
  *(_OWORD *)(LogMetadataAddress + 16) = 0;
  *(_OWORD *)(LogMetadataAddress + 32) = 0;
  *(_QWORD *)(LogMetadataAddress + 48) = 0;
  v73 = EntryHeaderSize + *(_DWORD *)v25 - *((_DWORD *)v25 + 2);
  *(_QWORD *)((char *)v25 + 28) = 8;
  *((_DWORD *)v25 + 6) = v73;
  *((_DWORD *)v25 + 9) = EntryHeaderSize;
  v28 = *((_QWORD *)v25 + 2);
  if ( !v28 )
    return 3221225626LL;
  v26 = v88;
  v14 = a4;
  v16 = a8;
  v12 = a6;
  v29 = v86;
LABEL_17:
  FormatRedoRecord(v28, v94, v26, a3, *(unsigned __int8 *)(v95 + 8), v14, a5, v12, a7, v16, v85);
  v30 = v96;
  *(_DWORD *)(v28 + 44) = 0;
  *(_QWORD *)(v28 + 24) = *(_QWORD *)(v30 + 2064);
  *(_QWORD *)(v28 + 32) = *(_QWORD *)(v30 + 2072);
  if ( v87 )
  {
    if ( !v93 )
      goto LABEL_45;
LABEL_94:
    _InterlockedAdd(v93, 0xFFFFF000);
    *(_DWORD *)(v13 + 48) += 4096;
    *((_DWORD *)v25 + 10) = 4096;
    goto LABEL_45;
  }
  if ( v93 )
    goto LABEL_94;
  if ( !v29 )
  {
    v31 = (*((_DWORD *)v25 + 6) + 4095) & 0xFFFFF000;
    while ( 1 )
    {
      v32 = *(unsigned int *)(v20 + 288);
      v33 = *(_QWORD *)(v20 + 72);
      v34 = (KSPIN_LOCK *)(v33 + 3776);
      v35 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v33 + 3776));
      v36 = *(_QWORD *)(v33 + 3704);
      v37 = *(unsigned int *)(v33 + 32);
      if ( ML_LSN_INVALID == v36 )
      {
        v38 = *(unsigned int *)(v33 + 24);
        v39 = *(_DWORD *)(v33 + 3664);
        v90 = v39 * ((unsigned int)v37 - v38);
      }
      else
      {
        v90 = *(unsigned int *)(v33 + 3664) * (v37 + (unsigned int)v36 - (unsigned __int64)*(unsigned int *)(v33 + 24));
        v39 = *(_DWORD *)(v33 + 3664);
        LODWORD(v38) = *(_DWORD *)(v33 + 24);
      }
      v40 = ML_LSN_INVALID == v36
          ? (unsigned int)v38 + *(unsigned int *)(v33 + 3696) - (unsigned __int64)(unsigned int)v37
          : (unsigned int)v38 - (unsigned __int64)(unsigned int)v37;
      v41 = v39 * v40;
      KeReleaseSpinLock(v34, v35);
      if ( v31 + (unsigned int)v32 > v41 && !DbgIgnoreLogFull )
        break;
      if ( !*(_BYTE *)(*(_QWORD *)(v20 + 80) + 2752LL)
        && 100 * (v90 + v32) / (v41 + v90) >= (unsigned __int8)byte_14026907A )
      {
        KeSetEvent(&LazyWriterScanEvent, 0, 0);
      }
      if ( (_DWORD)v32 == _InterlockedCompareExchange((volatile signed __int32 *)(v20 + 288), v31 + v32, v32) )
      {
        v13 = v97;
        v26 = v88;
        v29 = v86;
        *(_DWORD *)(v97 + 48) += v31;
        *((_DWORD *)v25 + 10) = v31;
        goto LABEL_45;
      }
    }
    if ( dword_1402473A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
    {
      v78 = *(_QWORD *)CmsDurableLog::LastWrittenLsn(v20, &v97);
      v79 = *(_QWORD *)CmsDurableLog::GetOldestRecordReference(v20, &v96, 0);
      v80 = *(_QWORD *)CmsDurableLog::BaseLsn(v20, &v95);
      LogFullPercentage = CmsDurableLog::GetLogFullPercentage((CmsDurableLog *)v20);
      ActivityIdThread = IoGetActivityIdThread(v83, v82);
      McTemplateK0qqiii_EtwWriteTransfer(
        (unsigned int)MinstoreEventProvider_Context,
        (unsigned int)LogFullRedoLog,
        ActivityIdThread,
        v32,
        LogFullPercentage,
        v80,
        v79,
        v78);
    }
    v42 = *(_QWORD *)v25;
    if ( !*(_QWORD *)v25 )
      goto LABEL_60;
    v43 = *(_QWORD *)(v42 - 16);
    v44 = (struct _SLIST_ENTRY *)(v42 - 16);
    if ( !v43 )
      goto LABEL_93;
    if ( *(_BYTE *)(v43 + 8) )
    {
      v45 = (struct _NPAGED_LOOKASIDE_LIST *)(v43 + 64);
      if ( *(_BYTE *)(v43 + 9) )
        ExFreeToNPagedLookasideList(v45, v44);
      else
        ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v45, v44);
      goto LABEL_60;
    }
    v77 = *(_QWORD *)(v43 + 88);
    if ( (int)v77 < *(_DWORD *)(v43 + 80) || SHIDWORD(v77) >= (int)v77 )
    {
      ExpInterlockedPushEntrySList((PSLIST_HEADER)(v43 + 64), v44);
      _InterlockedIncrement((volatile signed __int32 *)(v43 + 88));
    }
    else
    {
LABEL_93:
      ExFreePoolWithTag(v44, 0);
    }
LABEL_60:
    ExFreePoolWithTag(v25, 0);
    return 3221225864LL;
  }
LABEL_45:
  *((_DWORD *)v25 + 7) += v26;
  v52 = *(_QWORD *)v13 == 0;
  *(_QWORD *)(v13 + 40) = v94;
  if ( v52 )
    *(_QWORD *)v13 = v28;
  v53 = *(_QWORD *)(v13 + 8);
  if ( v53 )
    *(_QWORD *)(v53 + 48) = v28;
  *(_QWORD *)(v13 + 8) = v28;
  if ( !v29 )
  {
    if ( !*(_QWORD *)(v13 + 24) )
      *(_QWORD *)(v13 + 24) = v25;
    v54 = *(_QWORD *)(v13 + 32);
    if ( v54 )
    {
      **(_DWORD **)(v54 + 8) = *(_DWORD *)(v54 + 28) - 8;
      *(_DWORD *)(*(_QWORD *)(v54 + 8) + 4LL) = *(_DWORD *)(v54 + 16) - *(_DWORD *)(v54 + 8);
      *(_DWORD *)(v54 + 32) = *(_DWORD *)(v54 + 28);
      *(_QWORD *)(*(_QWORD *)(v13 + 32) + 48LL) = v25;
    }
    *(_QWORD *)(v13 + 32) = v25;
  }
  return 0;
}

```

## disassembly

```asm
0x14007d820  push    rbp
0x14007d822  push    rbx
0x14007d823  push    rsi
0x14007d824  push    rdi
0x14007d825  push    r12
0x14007d827  push    r13
0x14007d829  push    r15
0x14007d82b  lea     rbp, [rsp-60h]
0x14007d830  sub     rsp, 160h
0x14007d837  mov     rax, cs:__security_cookie
0x14007d83e  xor     rax, rsp
0x14007d841  mov     [rbp+90h+var_40], rax
0x14007d845  mov     rax, [rbp+90h+arg_50]
0x14007d84c  mov     rbx, rdx
0x14007d84f  mov     r11, [rbp+90h+arg_28]
0x14007d856  mov     r12, rcx
0x14007d859  mov     [rbp+90h+var_F8], rax
0x14007d85d  mov     r10, r9
0x14007d860  mov     [rsp+190h+var_118], r9
0x14007d865  mov     rax, [rbx+18h]
0x14007d869  mov     r9, [rbp+90h+arg_38]
0x14007d870  mov     [rbp+90h+var_F0], rdx
0x14007d874  mov     rdx, [rdx+70h]
0x14007d878  mov     rax, [rax+48h]
0x14007d87c  mov     [rbp+90h+var_D8], rcx
0x14007d880  mov     rcx, [rbp+90h+arg_20]
0x14007d887  mov     [rsp+190h+var_128], r8d
0x14007d88c  lea     r15, [rax+0B00h]
0x14007d893  mov     [rsp+190h+var_120], rcx
0x14007d898  mov     [rbp+90h+var_108], r11
0x14007d89c  mov     [rbp+90h+var_110], r9
0x14007d8a0  mov     [rbp+90h+var_E8], rdx
0x14007d8a4  mov     [rbp+90h+var_E0], rax
0x14007d8a8  mov     [rsp+190h+var_12E], 0
0x14007d8ad  cmp     rbx, [r12+28h]
0x14007d8b2  jnz     loc_14007DD32
0x14007d8b8  xor     esi, esi
0x14007d8ba  mov     [rsp+190h+var_130], 1
0x14007d8bf  mov     edi, esi
0x14007d8c1  mov     ebx, 38h ; '8'
0x14007d8c6  jmp     short loc_14007D8D1
0x14007d8c8  mov     rcx, [rsp+190h+var_120]
0x14007d8cd  mov     r9, [rbp+90h+var_110]
0x14007d8d1  test    r10, r10
0x14007d8d4  jz      short loc_14007D8E2
0x14007d8d6  mov     ebx, [r10]
0x14007d8d9  add     ebx, 7
0x14007d8dc  and     ebx, 0FFFFFFF8h
0x14007d8df  add     ebx, 40h ; '@'
0x14007d8e2  test    rcx, rcx
0x14007d8e5  jz      short loc_14007D8F4
0x14007d8e7  mov     eax, [rcx]
0x14007d8e9  add     ebx, 8
0x14007d8ec  add     eax, 7
0x14007d8ef  and     eax, 0FFFFFFF8h
0x14007d8f2  add     ebx, eax
0x14007d8f4  test    r11, r11
0x14007d8f7  mov     edx, esi
0x14007d8f9  mov     r8d, esi
0x14007d8fc  cmovnz  edx, [rbp+90h+arg_30]
0x14007d903  test    edx, edx
0x14007d905  jnz     loc_14007DE70
0x14007d90b  test    r9, r9
0x14007d90e  jnz     loc_14007DF2D
0x14007d914  mov     r13, [r12+20h]
0x14007d919  add     ebx, 7
0x14007d91c  add     ebx, edi
0x14007d91e  mov     [rsp+190h+arg_10], r14
0x14007d926  and     ebx, 0FFFFFFF8h
0x14007d929  mov     [rsp+190h+var_12C], ebx
0x14007d92d  test    r13, r13
0x14007d930  jz      loc_14007DB74
0x14007d936  mov     ecx, [r13+1Ch]
0x14007d93a  mov     eax, [r13+18h]
0x14007d93e  sub     eax, ecx
0x14007d940  cmp     eax, ebx
0x14007d942  jbe     loc_14007DB74
0x14007d948  mov     r14, [r13+8]
0x14007d94c  xorps   xmm0, xmm0
0x14007d94f  add     r14, rcx
0x14007d952  mov     dil, 1
0x14007d955  xor     eax, eax
0x14007d957  mov     [rsp+190h+var_12F], dil
0x14007d95c  movups  xmmword ptr [r14], xmm0
0x14007d960  movups  xmmword ptr [r14+10h], xmm0
0x14007d965  movups  xmmword ptr [r14+20h], xmm0
0x14007d96a  mov     [r14+30h], rax
0x14007d96e  test    r14, r14
0x14007d971  jz      loc_14007DB89
0x14007d977  movzx   ecx, [rsp+190h+var_130]
0x14007d97c  mov     r8d, ebx
0x14007d97f  mov     rax, [rbp+90h+var_E8]
0x14007d983  mov     rdx, [rbp+90h+var_F0]
0x14007d987  mov     [rsp+190h+var_140], cl
0x14007d98b  mov     ecx, [rbp+90h+arg_30]
0x14007d991  movzx   eax, byte ptr [rax+8]
0x14007d995  mov     [rsp+190h+var_148], r9
0x14007d99a  mov     r9d, [rsp+190h+var_128]
0x14007d99f  mov     [rsp+190h+var_150], ecx
0x14007d9a3  mov     rcx, [rsp+190h+var_120]
0x14007d9a8  mov     [rsp+190h+var_158], r11
0x14007d9ad  mov     [rsp+190h+var_160], rcx
0x14007d9b2  mov     rcx, r14
0x14007d9b5  mov     [rsp+190h+var_168], r10
0x14007d9ba  mov     [rsp+190h+var_170], eax
0x14007d9be  call    ?FormatRedoRecord@@YAXPEAU_SmsRedoRecord@@PEAVCmsBPlusTable@@KW4_MS_REDO_OPERATION@@KPEBU_CmsKey@@PEBU_CmsData@@4K1E@Z; FormatRedoRecord(_SmsRedoRecord *,CmsBPlusTable *,ulong,_MS_REDO_OPERATION,ulong,_CmsKey const *,_CmsData const *,_CmsData const *,ulong,CmsBPlusTable *,uchar)
0x14007d9c3  cmp     [rsp+190h+var_12E], 0
0x14007d9c8  mov     rcx, [rbp+90h+var_E0]
0x14007d9cc  mov     [r14+2Ch], esi
0x14007d9d0  mov     rax, [rcx+810h]
0x14007d9d7  mov     [r14+18h], rax
0x14007d9db  mov     rax, [rcx+818h]
0x14007d9e2  mov     [r14+20h], rax
0x14007d9e6  mov     rax, [rbp+90h+var_F8]
0x14007d9ea  jnz     loc_14007DC2B
0x14007d9f0  test    rax, rax
0x14007d9f3  jnz     loc_14007E04C
0x14007d9f9  test    dil, dil
0x14007d9fc  jnz     loc_14007DC34
0x14007da02  mov     esi, [r13+18h]
0x14007da06  add     esi, 0FFFh
0x14007da0c  and     esi, 0FFFFF000h
0x14007da12  mov     r12d, [r15+120h]
0x14007da19  mov     rbx, [r15+48h]
0x14007da1d  lea     rdi, [rbx+0EC0h]
0x14007da24  mov     rcx, rdi; SpinLock
0x14007da27  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14007da2e  nop     dword ptr [rax+rax+00h]
0x14007da33  mov     r10, [rbx+0E78h]
0x14007da3a  movzx   r9d, al
0x14007da3e  mov     rcx, cs:ML_LSN_INVALID
0x14007da45  mov     edx, [rbx+20h]
0x14007da48  cmp     rcx, r10
0x14007da4b  jnz     loc_14007DAED
0x14007da51  mov     r8d, [rbx+18h]
0x14007da55  mov     eax, edx
0x14007da57  mov     r11d, [rbx+0E50h]
0x14007da5e  sub     rax, r8
0x14007da61  imul    rax, r11
0x14007da65  mov     [rsp+190h+var_120], rax
0x14007da6a  mov     eax, edx
0x14007da6c  cmp     rcx, r10
0x14007da6f  jnz     short loc_14007DAE5
0x14007da71  mov     ebx, [rbx+0E70h]
0x14007da77  sub     rbx, rax
0x14007da7a  mov     eax, r8d
0x14007da7d  add     rbx, rax
0x14007da80  mov     eax, r11d
0x14007da83  movzx   edx, r9b; NewIrql
0x14007da87  mov     rcx, rdi; SpinLock
0x14007da8a  imul    rbx, rax
0x14007da8e  call    cs:__imp_KeReleaseSpinLock
0x14007da95  nop     dword ptr [rax+rax+00h]
0x14007da9a  lea     edi, [rsi+r12]
0x14007da9e  mov     eax, edi
0x14007daa0  cmp     rax, rbx
0x14007daa3  ja      short loc_14007DB14
0x14007daa5  mov     rax, [r15+50h]
0x14007daa9  cmp     byte ptr [rax+0AC0h], 0
0x14007dab0  jz      loc_14007DFD8
0x14007dab6  nop
0x14007dab7  mov     eax, r12d
0x14007daba  lock cmpxchg [r15+120h], edi
0x14007dac3  nop
0x14007dac4  jnz     loc_14007DA12
0x14007daca  mov     r12, [rbp+90h+var_D8]
0x14007dace  mov     ebx, [rsp+190h+var_12C]
0x14007dad2  movzx   edi, [rsp+190h+var_12F]
0x14007dad7  add     [r12+30h], esi
0x14007dadc  mov     [r13+28h], esi
0x14007dae0  jmp     loc_14007DC34
0x14007dae5  mov     ebx, r8d
0x14007dae8  sub     rbx, rax
0x14007daeb  jmp     short loc_14007DA80
0x14007daed  mov     r8d, [rbx+0E50h]
0x14007daf4  mov     eax, [rbx+18h]
0x14007daf7  mov     r11d, r10d
0x14007dafa  sub     r11, rax
0x14007dafd  add     r11, rdx
0x14007db00  imul    r11, r8
0x14007db04  mov     [rsp+190h+var_120], r11
0x14007db09  mov     r11d, r8d
0x14007db0c  mov     r8d, eax
0x14007db0f  jmp     loc_14007DA6A
0x14007db14  cmp     cs:?DbgIgnoreLogFull@@3KA, 0; ulong DbgIgnoreLogFull
0x14007db1b  jnz     short loc_14007DAA5
0x14007db1d  cmp     cs:dword_1402473A4, 1
0x14007db24  jz      loc_14007DF1B
0x14007db2a  mov     r8, [r13+0]
0x14007db2e  test    r8, r8
0x14007db31  jz      loc_14007DCDA
0x14007db37  mov     rbx, [r8-10h]
0x14007db3b  add     r8, 0FFFFFFFFFFFFFFF0h
0x14007db3f  test    rbx, rbx
0x14007db42  jz      loc_14007E036
0x14007db48  cmp     byte ptr [rbx+8], 0
0x14007db4c  jz      loc_14007E01A
0x14007db52  cmp     byte ptr [rbx+9], 0
0x14007db56  lea     rcx, [rbx+40h]; Lookaside
0x14007db5a  mov     rdx, r8; Entry
0x14007db5d  jnz     loc_14007DCCE
0x14007db63  call    cs:__imp_ExFreeToPagedLookasideList
0x14007db6a  nop     dword ptr [rax+rax+00h]
0x14007db6f  jmp     loc_14007DCDA
0x14007db74  xor     dil, dil
0x14007db77  mov     [rsp+190h+var_12F], dil
0x14007db7c  cmp     [rbp+90h+arg_48], dil
0x14007db83  jnz     loc_14007DF52
0x14007db89  mov     edx, 48h ; 'H'
0x14007db8e  mov     ecx, 42h ; 'B'
0x14007db93  mov     r8d, 6950534Dh
0x14007db99  call    cs:__imp_ExAllocatePool2
0x14007dba0  nop     dword ptr [rax+rax+00h]
0x14007dba5  mov     r13, rax
0x14007dba8  test    rax, rax
0x14007dbab  jz      loc_14007DCA2
0x14007dbb1  xor     edx, edx; Val
0x14007dbb3  mov     r8d, 48h ; 'H'; Size
0x14007dbb9  mov     rcx, rax; void *
0x14007dbbc  call    memset
0x14007dbc1  mov     rcx, [r15+48h]
0x14007dbc5  lea     edx, [rbx+8]
0x14007dbc8  call    LogGetEntryHeaderSize
0x14007dbcd  xor     ecx, ecx; ProcNumber
0x14007dbcf  mov     edi, eax
0x14007dbd1  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007dbd8  nop     dword ptr [rax+rax+00h]
0x14007dbdd  xor     edx, edx
0x14007dbdf  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14007dbe5  lea     rbx, [rdx+rdx*2]
0x14007dbe9  shl     rbx, 6
0x14007dbed  add     rbx, cs:qword_140269440
0x14007dbf4  cmp     edi, [rbx]
0x14007dbf6  jbe     loc_14007DCF2
0x14007dbfc  mov     rbx, rsi
0x14007dbff  lea     rdx, [rdi+10h]
0x14007dc03  mov     ecx, 42h ; 'B'
0x14007dc08  mov     r8d, 6950534Dh
0x14007dc0e  call    cs:__imp_ExAllocatePool2
0x14007dc15  nop     dword ptr [rax+rax+00h]
0x14007dc1a  test    al, 0Fh
0x14007dc1c  jz      short loc_14007DC88
0x14007dc1e  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14007dc25  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14007dc2b  test    rax, rax
0x14007dc2e  jnz     loc_14007E04C
0x14007dc34  add     [r13+1Ch], ebx
0x14007dc38  cmp     qword ptr [r12], 0
0x14007dc3d  mov     rax, [rbp+90h+var_F0]
0x14007dc41  mov     [r12+28h], rax
0x14007dc46  jnz     short loc_14007DC4C
0x14007dc48  mov     [r12], r14
0x14007dc4c  mov     rax, [r12+8]
0x14007dc51  test    rax, rax
0x14007dc54  jz      short loc_14007DC5A
0x14007dc56  mov     [rax+30h], r14
0x14007dc5a  mov     [r12+8], r14
0x14007dc5f  test    dil, dil
0x14007dc62  jnz     short loc_14007DC84
0x14007dc64  cmp     qword ptr [r12+18h], 0
0x14007dc6a  jnz     short loc_14007DC71
0x14007dc6c  mov     [r12+18h], r13
0x14007dc71  mov     rdx, [r12+20h]
0x14007dc76  test    rdx, rdx
0x14007dc79  jnz     loc_14007E06B
0x14007dc7f  mov     [r12+20h], r13
0x14007dc84  xor     eax, eax
0x14007dc86  jmp     short loc_14007DCA7
0x14007dc88  test    rax, rax
0x14007dc8b  jnz     loc_14007DE9C
0x14007dc91  xor     edx, edx; Tag
0x14007dc93  mov     rcx, r13; P
0x14007dc96  call    cs:__imp_ExFreePoolWithTag
0x14007dc9d  nop     dword ptr [rax+rax+00h]
0x14007dca2  mov     eax, 0C000009Ah
0x14007dca7  mov     r14, [rsp+190h+arg_10]
0x14007dcaf  mov     rcx, [rbp+90h+var_40]
0x14007dcb3  xor     rcx, rsp; StackCookie
0x14007dcb6  call    __security_check_cookie
0x14007dcbb  add     rsp, 160h
0x14007dcc2  pop     r15
0x14007dcc4  pop     r13
0x14007dcc6  pop     r12
0x14007dcc8  pop     rdi
0x14007dcc9  pop     rsi
0x14007dcca  pop     rbx
0x14007dccb  pop     rbp
0x14007dccc  retn
0x14007dcce  call    cs:__imp_ExFreeToNPagedLookasideList
0x14007dcd5  nop     dword ptr [rax+rax+00h]
0x14007dcda  xor     edx, edx; Tag
0x14007dcdc  mov     rcx, r13; P
0x14007dcdf  call    cs:__imp_ExFreePoolWithTag
0x14007dce6  nop     dword ptr [rax+rax+00h]
0x14007dceb  mov     eax, 0C0000188h
0x14007dcf0  jmp     short loc_14007DCA7
0x14007dcf2  cmp     byte ptr [rbx+8], 0
0x14007dcf6  jnz     loc_14007DF9C
0x14007dcfc  mov     rcx, [rbx+58h]
0x14007dd00  mov     rax, rcx
  ... truncated ...
```
