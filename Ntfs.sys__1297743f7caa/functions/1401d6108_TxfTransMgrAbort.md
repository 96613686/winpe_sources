# TxfTransMgrAbort

- ea: `0x1401d6108`
- end: `0x1401d6992`
- name: `TxfTransMgrAbort`
- size: `2186`
- prototype: ``
- caller_count: `3`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400f9d98`
- `0x1401d9840`
- `0x140267110`

## callees

- `0x1400082b0`
- `0x140010be0`
- `0x140012ab0`
- `0x140012b50`
- `0x140016ea0`
- `0x140017030`
- `0x1400291f0`
- `0x140029d80`
- `0x140038908`
- `0x1400520e4`
- `0x140053c24`
- `0x1400592c0`
- `0x140059740`
- `0x1400b62e4`
- `0x14012e540`
- `0x140140fac`
- `0x140188d34`
- `0x14018e688`
- `0x1401c2b38`
- `0x1401d6108`
- `0x1401d8390`
- `0x1401da980`
- `0x1401daab8`
- `0x1401db394`
- `0x1401dc59c`
- `0x14020570c`
- `0x140209960`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401d68ba`
- `ntoskrnl!KeSetEvent` at `0x1401d68ba`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401d63d3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401d63d3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d6298`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d6298`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d61a2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d61a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d6219`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d6256`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d6219`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d6256`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d63fd`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d65ea`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d63fd`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401d65ea`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d641c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d6609`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d641c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401d6609`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6562`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d65cf`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6674`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6562`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d65cf`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x1401d6674`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReserveAndAppendLog` at `0x1401d67ae`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReserveAndAppendLog` at `0x1401d67ae`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d659b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1401d659b`

## pseudocode

```c
__int64 __fastcall TxfTransMgrAbort(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  CLFS_LSN *v3; // rdi
  __int64 v4; // r13
  struct _ERESOURCE *v5; // rcx
  __int64 v6; // rdx
  int v8; // ebx
  volatile signed __int32 *v9; // rsi
  int v10; // eax
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  void *v14; // rcx
  int v15; // eax
  unsigned __int64 v16; // rcx
  __int64 v17; // r8
  unsigned __int8 v18; // cf
  int v19; // eax
  unsigned __int64 v20; // rax
  __int64 v21; // r8
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  unsigned __int64 v26; // rax
  __int64 v27; // r8
  volatile signed __int32 *v28; // r12
  int v29; // eax
  NTSTATUS appended; // eax
  NTSTATUS v31; // edx
  unsigned __int64 v32; // rcx
  __int64 v33; // r8
  unsigned __int64 v34; // rax
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r9
  char v39; // [rsp+50h] [rbp-128h]
  __int64 rgcbReservation; // [rsp+58h] [rbp-120h] BYREF
  CLFS_LSN plsn; // [rsp+60h] [rbp-118h] BYREF
  CLFS_LSN v42; // [rsp+68h] [rbp-110h] BYREF
  CLFS_LSN *v43; // [rsp+70h] [rbp-108h] BYREF
  volatile signed __int32 *v44; // [rsp+78h] [rbp-100h] BYREF
  _QWORD v45[4]; // [rsp+80h] [rbp-F8h] BYREF
  CLFS_WRITE_ENTRY v46; // [rsp+A0h] [rbp-D8h] BYREF
  _OWORD v47[2]; // [rsp+B0h] [rbp-C8h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-A8h]
  _WORD v49[48]; // [rsp+E0h] [rbp-98h] BYREF

  v2 = a2;
  rgcbReservation = a2;
  v3 = (CLFS_LSN *)a1;
  v43 = (CLFS_LSN *)a1;
  v45[2] = a2;
  memset(v47, 0, sizeof(v47));
  v48 = 0;
  plsn.ullOffset = 0;
  v45[0] = a2 + 208;
  v4 = *(_QWORD *)(a2 + 208);
  v42.ullOffset = 0;
  TxfTransFreeze(a2, 1);
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v2 + 24) + 80LL), 1u);
  if ( (!v3 || (v3[2].offset.idxRecord & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
  {
    McTemplateU0spjpj_EtwWriteTransfer(
      v4 + 672,
      (unsigned int)txftrans_c7455,
      (unsigned int)"TxfTransMgrAbort",
      v4,
      v4 + 672,
      v2,
      v2 + 256);
  }
  v5 = (struct _ERESOURCE *)(*(_QWORD *)(v2 + 24) + 80LL);
  if ( (*(_DWORD *)(v2 + 16) & 0x2000) != 0 )
  {
    ExReleaseResourceLite(v5);
    v44 = (volatile signed __int32 *)v2;
    LOBYTE(v6) = 1;
    TxfDereferenceTransaction(&v44, v6);
    return 0;
  }
  v45[1] = v4;
  v39 = 0;
  v8 = 0;
  v45[3] = v2 + 16;
  ExReleaseResourceLite(v5);
  v44 = (volatile signed __int32 *)(v4 + 232);
  if ( _InterlockedIncrement((volatile signed __int32 *)(v4 + 232)) > 10 )
  {
    v9 = (volatile signed __int32 *)(v4 + 232);
    do
    {
      _InterlockedDecrement(v9);
      KeWaitForSingleObject((PVOID)(*(_QWORD *)(v4 + 24) + 72LL), Executive, 0, 0, 0);
    }
    while ( _InterlockedIncrement(v9) > 10 );
    v2 = rgcbReservation;
  }
  if ( !v3 )
  {
    rgcbReservation = NtfsInitializeTopLevelIrp(v47, 3, *(_QWORD *)(v4 + 16));
    v8 = NtfsInitializeIrpContextInternal(0, 1, 0, (__int64 *)&v43);
    v3 = v43;
    if ( !v43 )
    {
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x8000000) != 0 )
        McTemplateU0sdpjpj_EtwWriteTransfer(
          v2 + 256,
          (unsigned int)txftrans_c7553,
          (unsigned int)"TxfTransMgrAbort",
          v8,
          v2,
          v2 + 256,
          v4,
          v4 + 672);
      goto LABEL_79;
    }
    NtfsUpdateIrpContextWithTopLevel(v43, rgcbReservation);
    v39 = 1;
  }
  NtfsSetIrpContextVcb(v3, *(_QWORD *)(v4 + 16));
  v3[1].offset.cidContainer |= 0x10001u;
  v3[54].offset.cidContainer |= 0x100000u;
  v3[54].offset.cidContainer |= 0x80008u;
  v10 = *(_DWORD *)(v2 + 16);
  if ( (v10 & 0x40) == 0 )
    goto LABEL_79;
  if ( (v10 & 8) == 0 )
  {
    while ( 1 )
    {
      v11 = (_QWORD *)(v2 + 176);
      v12 = *(_QWORD **)(v2 + 176);
      if ( v12 == (_QWORD *)(v2 + 176) )
        break;
      if ( (_QWORD *)v12[1] != v11 || (v13 = *v12, *(_QWORD **)(*v12 + 8LL) != v12) )
        __fastfail(3u);
      *v11 = v13;
      *(_QWORD *)(v13 + 8) = v11;
      v14 = (void *)v12[4];
      if ( v14 )
        TxfDereferenceTxfFcb(v14);
      ExFreeToLookasideListEx(&TxfDeletedLinkLookasideList, v12);
    }
  }
  if ( (*(_DWORD *)(v2 + 16) & 0x20) == 0 )
    v3[54].offset.cidContainer |= 0x40u;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v4 + 8912));
  v42 = *(CLFS_LSN *)(v4 + 8920);
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v4 + 8912));
  v15 = TxfActOnAllStreamsForTransaction((_DWORD)v3, 2, &v42);
  v8 = v15;
  if ( v15 >= 0 )
  {
    TxfTransCleanupTxfWriterInformation(v3, v2, 0);
    v19 = TxfUsnProcessingForFilesOnModifiedListAtEOT((int)v3);
    v8 = v19;
    if ( v19 < 0 )
    {
      if ( v19 != -1073741801 )
      {
        v20 = (unsigned int)(v19 + 1073741697);
        if ( (unsigned int)v20 > 0x22 || (v21 = 0x408000001LL, !_bittest64(&v21, v20)) )
        {
          if ( v8 == -1072037845
            || v8 == -1073741202
            || v8 == -1073741435
            || v8 == -1073741496
            || (v22 = (unsigned int)(v8 + 1073741667), (unsigned int)v22 <= 0x23)
            && (v23 = 0x800000041LL, _bittest64(&v23, v22))
            || (unsigned int)(v8 + 1073741811) <= 0x15 && (v24 = 2097219, _bittest(&v24, v8 + 1073741811))
            || v8 == -2147483626
            || v8 == -1072037841 )
          {
            ++LODWORD((*TxfData)[2]);
          }
          goto LABEL_79;
        }
      }
      goto LABEL_32;
    }
    _InterlockedOr((volatile signed __int32 *)(v2 + 16), 8u);
    plsn = *(CLFS_LSN *)(v2 + 48);
    if ( ClfsLsnNull(&plsn) )
    {
      ProcessSavepointListForCurrentLogRec(v2);
    }
    else
    {
      do
      {
        if ( ClfsLsnNull(&plsn) )
          break;
        NtfsPurgeFileRecordCache(v3);
        v8 = TxfTransDoNextUndo((__int64)v3, (CLFS_LSN *)v2, &plsn);
      }
      while ( v8 >= 0 );
    }
    if ( *(_QWORD *)(v2 + 224) )
    {
      NtfsPurgeFileRecordCache(v3);
      v3->offset.cidContainer |= 0x200u;
      ClfsTerminateReadLog(*(PVOID *)(v2 + 224));
      v3->offset.cidContainer &= ~0x200u;
      *(_QWORD *)(v2 + 224) = 0;
      _InterlockedDecrement((volatile signed __int32 *)(v4 + 528));
    }
    if ( v8 < 0 )
      goto LABEL_79;
    _InterlockedOr((volatile signed __int32 *)(v2 + 16), 0x100u);
    if ( !ClfsLsnNull((const CLFS_LSN *)(v2 + 40)) )
    {
      ExAcquireFastMutex(*(PFAST_MUTEX *)(v4 + 8912));
      v42 = *(CLFS_LSN *)(v4 + 8920);
      ExReleaseFastMutex(*(PFAST_MUTEX *)(v4 + 8912));
      v25 = TxfActOnAllStreamsForTransaction((_DWORD)v3, 9, &v42);
      v8 = v25;
      if ( v25 < 0 )
      {
        if ( v25 == -1073741801 )
          goto LABEL_32;
        v26 = (unsigned int)(v25 + 1073741697);
        if ( (unsigned int)v26 > 0x22 )
          goto LABEL_79;
        v27 = 0x408000001LL;
        v18 = _bittest64(&v27, v26);
LABEL_31:
        if ( v18 )
          goto LABEL_32;
        goto LABEL_79;
      }
      LfsQueryLastLsn(*(_QWORD *)(v3[13].ullOffset + 232));
      LfsFlushToLsn(*(_QWORD *)(v3[13].ullOffset + 232), NtfsLargeMax);
      *(_DWORD *)(v3[18].ullOffset + 24) = 0;
    }
    memset(v49, 0, sizeof(v49));
    v49[0] = 8;
    v28 = (volatile signed __int32 *)(v2 + 16);
    v29 = *(_DWORD *)(v2 + 16) & 0x20;
    v46.Buffer = v49;
    v46.ByteLength = 96;
    TxfTransWriteLogArray(v2, &v46, 1u, v29 != 0 ? 2 : 6, v3, 0, 0, 0, 0);
    if ( (*(_DWORD *)(v2 + 16) & 0x61) == 0x40 )
    {
      rgcbReservation = -96;
      NtfsPurgeFileRecordCache(v3);
      v3->offset.cidContainer |= 0x200u;
      appended = ClfsReserveAndAppendLog(*(PVOID *)(v4 + 512), 0, 0, 0, 0, 1u, &rgcbReservation, 0, 0);
      v31 = appended;
      v3->offset.cidContainer &= ~0x200u;
      if ( appended )
      {
        if ( appended == -1073741801
          || (v32 = (unsigned int)(appended + 1073741697), (unsigned int)v32 <= 0x22)
          && (v33 = 0x408000001LL, _bittest64(&v33, v32)) )
        {
          ++HIDWORD((*TxfData)[1]);
        }
        else if ( appended == -1072037845
               || appended == -1073741202
               || appended == -1073741435
               || appended == -1073741496
               || (v34 = (unsigned int)(appended + 1073741667), (unsigned int)v34 <= 0x23)
               && (v35 = 0x800000041LL, _bittest64(&v35, v34))
               || (unsigned int)(v31 + 1073741811) <= 0x15 && (v36 = 2097219, _bittest(&v36, v31 + 1073741811))
               || v31 == -2147483626
               || v31 == -1072037841 )
        {
          ++LODWORD((*TxfData)[2]);
        }
      }
    }
    goto LABEL_80;
  }
  if ( v15 == -1073741801 )
  {
LABEL_32:
    ++HIDWORD((*TxfData)[1]);
    goto LABEL_79;
  }
  v16 = (unsigned int)(v15 + 1073741697);
  if ( (unsigned int)v16 <= 0x22 )
  {
    v17 = 0x408000001LL;
    v18 = _bittest64(&v17, v16);
    goto LABEL_31;
  }
LABEL_79:
  v28 = (volatile signed __int32 *)(v2 + 16);
LABEL_80:
  _InterlockedDecrement(v44);
  KeSetEvent((PRKEVENT)(*(_QWORD *)(v4 + 24) + 72LL), 0, 0);
  if ( v8 < 0 )
  {
    TxfSetupForDeferredAbortPriv(v2, v8, (unsigned int)"TxfTransMgrAbort", (unsigned int)"txftrans.c", 8121);
  }
  else
  {
    TxfTransCleanupOnTransEnd((__int64)v3, v2, 0, 0, 0);
    _InterlockedAnd(v28, 0xFFFFFFFE);
    TxfRemoveTransactionFromList(v2);
    _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)v45[0] + 248LL), 1u);
  }
  v45[0] = v2;
  LOBYTE(v37) = 1;
  TxfDereferenceTransaction(v45, v37);
  if ( v39 )
    v3[1].offset.cidContainer &= ~0x10000u;
  LOBYTE(v38) = 1;
  NtfsExtendedCompleteRequestInternal(v3, 0, 0, v38, 1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1401d6108  mov     [rsp+arg_10], rbx
0x1401d610d  mov     [rsp+arg_18], rsi
0x1401d6112  push    rdi
0x1401d6113  push    r12
0x1401d6115  push    r13
0x1401d6117  push    r14
0x1401d6119  push    r15
0x1401d611b  sub     rsp, 150h
0x1401d6122  mov     rax, cs:__security_cookie
0x1401d6129  xor     rax, rsp
0x1401d612c  mov     [rsp+178h+var_38], rax
0x1401d6134  mov     rsi, rdx
0x1401d6137  mov     [rsp+178h+var_120], rdx
0x1401d613c  mov     rdi, rcx
0x1401d613f  mov     [rsp+178h+var_108], rcx
0x1401d6144  mov     [rsp+178h+var_E8], rdx
0x1401d614c  xorps   xmm0, xmm0
0x1401d614f  xor     eax, eax
0x1401d6151  movups  [rsp+178h+var_C8], xmm0
0x1401d6159  movups  [rsp+178h+var_B8], xmm0
0x1401d6161  mov     [rsp+178h+var_A8], rax
0x1401d6169  xor     r14d, r14d
0x1401d616c  mov     qword ptr [rsp+178h+plsn], r14
0x1401d6171  lea     rax, [rdx+0D0h]
0x1401d6178  mov     [rsp+178h+var_F8], rax
0x1401d6180  mov     r13, [rax]
0x1401d6183  mov     [rsp+178h+var_110], r14
0x1401d6188  lea     r15d, [r14+1]
0x1401d618c  mov     edx, r15d
0x1401d618f  mov     rcx, rsi
0x1401d6192  call    TxfTransFreeze
0x1401d6197  mov     rcx, [rsi+18h]
0x1401d619b  add     rcx, 50h ; 'P'; Resource
0x1401d619f  mov     dl, r15b; Wait
0x1401d61a2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d61a9  nop     dword ptr [rax+rax+00h]
0x1401d61ae  test    rdi, rdi
0x1401d61b1  jz      short loc_1401D61C3
0x1401d61b3  mov     eax, [rdi+10h]
0x1401d61b6  bt      rax, 14h
0x1401d61bb  jnb     short loc_1401D61C3
0x1401d61bd  lea     r12d, [r14+8]
0x1401d61c1  jmp     short loc_1401D6205
0x1401d61c3  mov     r12d, 8
0x1401d61c9  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, r12b
0x1401d61d0  jz      short loc_1401D6205
0x1401d61d2  lea     rax, [rsi+100h]
0x1401d61d9  lea     rcx, [r13+2A0h]
0x1401d61e0  mov     [rsp+178h+rgcbReservation], rax
0x1401d61e5  mov     qword ptr [rsp+178h+cReserveRecords], rsi
0x1401d61ea  mov     [rsp+178h+Timeout], rcx
0x1401d61ef  mov     r9, r13
0x1401d61f2  lea     r8, aTxftransmgrabo; "TxfTransMgrAbort"
0x1401d61f9  lea     rdx, txftrans_c7455
0x1401d6200  call    McTemplateU0spjpj_EtwWriteTransfer
0x1401d6205  lea     rdx, [rsi+10h]
0x1401d6209  mov     rcx, [rsi+18h]
0x1401d620d  add     rcx, 50h ; 'P'; Resource
0x1401d6211  test    dword ptr [rdx], 2000h
0x1401d6217  jz      short loc_1401D623E
0x1401d6219  call    cs:__imp_ExReleaseResourceLite
0x1401d6220  nop     dword ptr [rax+rax+00h]
0x1401d6225  mov     [rsp+178h+var_100], rsi
0x1401d622a  mov     dl, r15b
0x1401d622d  lea     rcx, [rsp+178h+var_100]
0x1401d6232  call    TxfDereferenceTransaction
0x1401d6237  xor     eax, eax
0x1401d6239  jmp     loc_1401D6964
0x1401d623e  mov     [rsp+178h+var_F0], r13
0x1401d6246  mov     [rsp+178h+var_128], r14b
0x1401d624b  mov     ebx, r14d
0x1401d624e  mov     [rsp+178h+var_E0], rdx
0x1401d6256  call    cs:__imp_ExReleaseResourceLite
0x1401d625d  nop     dword ptr [rax+rax+00h]
0x1401d6262  lea     rcx, [r13+0E8h]
0x1401d6269  mov     [rsp+178h+var_100], rcx
0x1401d626e  mov     eax, r15d
0x1401d6271  lock xadd [rcx], eax
0x1401d6275  add     eax, r15d
0x1401d6278  cmp     eax, 0Ah
0x1401d627b  jle     short loc_1401D62B8
0x1401d627d  mov     rsi, rcx
0x1401d6280  lock dec dword ptr [rsi]
0x1401d6283  mov     rcx, [r13+18h]
0x1401d6287  add     rcx, 48h ; 'H'; Object
0x1401d628b  mov     [rsp+178h+Timeout], r14; Timeout
0x1401d6290  xor     r9d, r9d; Alertable
0x1401d6293  xor     r8d, r8d; WaitMode
0x1401d6296  xor     edx, edx; WaitReason
0x1401d6298  call    cs:__imp_KeWaitForSingleObject
0x1401d629f  nop     dword ptr [rax+rax+00h]
0x1401d62a4  mov     eax, r15d
0x1401d62a7  lock xadd [rsi], eax
0x1401d62ab  add     eax, r15d
0x1401d62ae  cmp     eax, 0Ah
0x1401d62b1  jg      short loc_1401D6280
0x1401d62b3  mov     rsi, [rsp+178h+var_120]
0x1401d62b8  test    rdi, rdi
0x1401d62bb  jnz     loc_1401D6358
0x1401d62c1  mov     r8, [r13+10h]
0x1401d62c5  lea     edx, [rdi+3]
0x1401d62c8  lea     rcx, [rsp+178h+var_C8]
0x1401d62d0  call    NtfsInitializeTopLevelIrp
0x1401d62d5  mov     [rsp+178h+var_120], rax
0x1401d62da  lea     r9, [rsp+178h+var_108]
0x1401d62df  xor     r8d, r8d
0x1401d62e2  mov     dl, r15b
0x1401d62e5  xor     ecx, ecx; Irp
0x1401d62e7  call    NtfsInitializeIrpContextInternal
0x1401d62ec  mov     ebx, eax
0x1401d62ee  mov     [rsp+178h+var_124], eax
0x1401d62f2  mov     rdi, [rsp+178h+var_108]
0x1401d62f7  test    rdi, rdi
0x1401d62fa  jnz     short loc_1401D6346
0x1401d62fc  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, r12b
0x1401d6303  jz      loc_1401D6868
0x1401d6309  lea     rax, [r13+2A0h]
0x1401d6310  lea     rcx, [rsi+100h]
0x1401d6317  mov     qword ptr [rsp+178h+fFlags], rax
0x1401d631c  mov     [rsp+178h+rgcbReservation], r13
0x1401d6321  mov     qword ptr [rsp+178h+cReserveRecords], rcx
0x1401d6326  mov     [rsp+178h+Timeout], rsi
0x1401d632b  mov     r9d, ebx
0x1401d632e  lea     r8, aTxftransmgrabo; "TxfTransMgrAbort"
0x1401d6335  lea     rdx, txftrans_c7553
0x1401d633c  call    McTemplateU0sdpjpj_EtwWriteTransfer
0x1401d6341  jmp     loc_1401D6868
0x1401d6346  mov     rdx, [rsp+178h+var_120]
0x1401d634b  mov     rcx, rdi
0x1401d634e  call    NtfsUpdateIrpContextWithTopLevel
0x1401d6353  mov     [rsp+178h+var_128], r15b
0x1401d6358  mov     rdx, [r13+10h]
0x1401d635c  mov     rcx, rdi
0x1401d635f  call    NtfsSetIrpContextVcb
0x1401d6364  or      dword ptr [rdi+0Ch], 10001h
0x1401d636b  bts     dword ptr [rdi+1B4h], 14h
0x1401d6373  mov     eax, [rdi+1B4h]
0x1401d6379  or      eax, 80008h
0x1401d637e  mov     [rdi+1B4h], eax
0x1401d6384  mov     eax, [rsi+10h]
0x1401d6387  test    al, 40h
0x1401d6389  jz      loc_1401D6868
0x1401d638f  test    r12b, al
0x1401d6392  jnz     short loc_1401D63E8
0x1401d6394  lea     rax, [rsi+0B0h]
0x1401d639b  mov     rbx, [rax]
0x1401d639e  cmp     rbx, rax
0x1401d63a1  jz      short loc_1401D63E8
0x1401d63a3  cmp     [rbx+8], rax
0x1401d63a7  jnz     short loc_1401D63E1
0x1401d63a9  mov     rcx, [rbx]
0x1401d63ac  cmp     [rcx+8], rbx
0x1401d63b0  jnz     short loc_1401D63E1
0x1401d63b2  mov     [rax], rcx
0x1401d63b5  mov     [rcx+8], rax
0x1401d63b9  mov     rcx, [rbx+20h]
0x1401d63bd  test    rcx, rcx
0x1401d63c0  jz      short loc_1401D63C9
0x1401d63c2  xor     edx, edx
0x1401d63c4  call    TxfDereferenceTxfFcb
0x1401d63c9  mov     rdx, rbx; Entry
0x1401d63cc  lea     rcx, TxfDeletedLinkLookasideList; Lookaside
0x1401d63d3  call    cs:__imp_ExFreeToLookasideListEx
0x1401d63da  nop     dword ptr [rax+rax+00h]
0x1401d63df  jmp     short loc_1401D6394
0x1401d63e1  mov     ecx, 3
0x1401d63e6  int     29h; Win8: RtlFailFast(ecx)
0x1401d63e8  mov     eax, [rsi+10h]
0x1401d63eb  test    al, 20h
0x1401d63ed  jnz     short loc_1401D63F6
0x1401d63ef  or      dword ptr [rdi+1B4h], 40h
0x1401d63f6  mov     rcx, [r13+22D0h]; FastMutex
0x1401d63fd  call    cs:__imp_ExAcquireFastMutex
0x1401d6404  nop     dword ptr [rax+rax+00h]
0x1401d6409  mov     rax, [r13+22D8h]
0x1401d6410  mov     [rsp+178h+var_110], rax
0x1401d6415  mov     rcx, [r13+22D0h]; FastMutex
0x1401d641c  call    cs:__imp_ExReleaseFastMutex
0x1401d6423  nop     dword ptr [rax+rax+00h]
0x1401d6428  lea     rax, [rsp+178h+var_110]
0x1401d642d  mov     qword ptr [rsp+178h+cReserveRecords], rax
0x1401d6432  mov     r8d, 2
0x1401d6438  mov     dword ptr [rsp+178h+Timeout], r8d
0x1401d643d  lea     r9d, [r8+9]
0x1401d6441  mov     rdx, rsi
0x1401d6444  mov     rcx, rdi
0x1401d6447  call    TxfActOnAllStreamsForTransaction
0x1401d644c  mov     ebx, eax
0x1401d644e  mov     [rsp+178h+var_124], eax
0x1401d6452  test    eax, eax
0x1401d6454  jns     short loc_1401D6490
0x1401d6456  cmp     eax, 0C0000017h
0x1401d645b  jz      short loc_1401D6480
0x1401d645d  lea     ecx, [rax+3FFFFF81h]
0x1401d6463  cmp     ecx, 22h ; '"'
0x1401d6466  ja      loc_1401D6868
0x1401d646c  mov     r8, 408000001h
0x1401d6476  bt      r8, rcx
0x1401d647a  jnb     loc_1401D6868
0x1401d6480  mov     rax, cs:TxfData
0x1401d6487  add     [rax+0Ch], r15d
0x1401d648b  jmp     loc_1401D6868
0x1401d6490  xor     r8d, r8d
0x1401d6493  mov     rdx, rsi
0x1401d6496  mov     rcx, rdi
0x1401d6499  call    TxfTransCleanupTxfWriterInformation
0x1401d649e  xor     r8d, r8d
0x1401d64a1  mov     rdx, rsi
0x1401d64a4  mov     rcx, rdi; int
0x1401d64a7  call    TxfUsnProcessingForFilesOnModifiedListAtEOT
0x1401d64ac  mov     ebx, eax
0x1401d64ae  mov     [rsp+178h+var_124], eax
0x1401d64b2  test    eax, eax
0x1401d64b4  jns     loc_1401D654F
0x1401d64ba  cmp     eax, 0C0000017h
0x1401d64bf  jz      short loc_1401D6480
0x1401d64c1  add     eax, 3FFFFF81h
0x1401d64c6  cmp     eax, 22h ; '"'
0x1401d64c9  ja      short loc_1401D64DB
0x1401d64cb  mov     r8, 408000001h
0x1401d64d5  bt      r8, rax
0x1401d64d9  jb      short loc_1401D6480
0x1401d64db  cmp     ebx, 0C01A002Bh
0x1401d64e1  jz      short loc_1401D653F
0x1401d64e3  cmp     ebx, 0C000026Eh
0x1401d64e9  jz      short loc_1401D653F
0x1401d64eb  cmp     ebx, 0C0000185h
0x1401d64f1  jz      short loc_1401D653F
0x1401d64f3  cmp     ebx, 0C0000148h
0x1401d64f9  jz      short loc_1401D653F
0x1401d64fb  lea     eax, [rbx+3FFFFF63h]
0x1401d6501  cmp     eax, 23h ; '#'
0x1401d6504  ja      short loc_1401D6516
0x1401d6506  mov     rcx, 800000041h
0x1401d6510  bt      rcx, rax
0x1401d6514  jb      short loc_1401D653F
0x1401d6516  lea     ecx, [rbx+3FFFFFF3h]
0x1401d651c  cmp     ecx, 15h
0x1401d651f  ja      short loc_1401D652B
0x1401d6521  mov     eax, 200043h
0x1401d6526  bt      eax, ecx
0x1401d6529  jb      short loc_1401D653F
0x1401d652b  cmp     ebx, 80000016h
0x1401d6531  jz      short loc_1401D653F
0x1401d6533  cmp     ebx, 0C01A002Fh
0x1401d6539  jnz     loc_1401D6868
0x1401d653f  mov     rax, cs:TxfData
0x1401d6546  add     [rax+10h], r15d
0x1401d654a  jmp     loc_1401D6868
0x1401d654f  lock or [rsi+10h], r12d
0x1401d6554  mov     rax, [rsi+30h]
0x1401d6558  mov     qword ptr [rsp+178h+plsn], rax
0x1401d655d  lea     rcx, [rsp+178h+plsn]; plsn
0x1401d6562  call    cs:__imp_ClfsLsnNull
0x1401d6569  nop     dword ptr [rax+rax+00h]
0x1401d656e  test    al, al
0x1401d6570  jz      loc_1401D666F
0x1401d6576  mov     rcx, rsi
0x1401d6579  call    ProcessSavepointListForCurrentLogRec
0x1401d657e  cmp     [rsi+0E0h], r14
0x1401d6585  jz      short loc_1401D65BB
0x1401d6587  mov     rcx, rdi
0x1401d658a  call    NtfsPurgeFileRecordCache
0x1401d658f  bts     dword ptr [rdi+4], 9
0x1401d6594  mov     rcx, [rsi+0E0h]; pvCursorContext
0x1401d659b  call    cs:__imp_ClfsTerminateReadLog
0x1401d65a2  nop     dword ptr [rax+rax+00h]
0x1401d65a7  btr     dword ptr [rdi+4], 9
0x1401d65ac  mov     [rsi+0E0h], r14
0x1401d65b3  lock dec dword ptr [r13+210h]
0x1401d65bb  test    ebx, ebx
0x1401d65bd  js      loc_1401D6868
0x1401d65c3  lock or dword ptr [rsi+10h], 100h
0x1401d65cb  lea     rcx, [rsi+28h]; plsn
0x1401d65cf  call    cs:__imp_ClfsLsnNull
0x1401d65d6  nop     dword ptr [rax+rax+00h]
0x1401d65db  test    al, al
0x1401d65dd  jnz     loc_1401D66E2
0x1401d65e3  mov     rcx, [r13+22D0h]; FastMutex
0x1401d65ea  call    cs:__imp_ExAcquireFastMutex
0x1401d65f1  nop     dword ptr [rax+rax+00h]
0x1401d65f6  mov     rax, [r13+22D8h]
0x1401d65fd  mov     [rsp+178h+var_110], rax
0x1401d6602  mov     rcx, [r13+22D0h]; FastMutex
0x1401d6609  call    cs:__imp_ExReleaseFastMutex
0x1401d6610  nop     dword ptr [rax+rax+00h]
0x1401d6615  lea     rax, [rsp+178h+var_110]
0x1401d661a  mov     qword ptr [rsp+178h+cReserveRecords], rax
0x1401d661f  mov     dword ptr [rsp+178h+Timeout], 9
0x1401d6627  xor     r9d, r9d
0x1401d662a  lea     r8d, [r9+64h]
0x1401d662e  mov     rdx, rsi
0x1401d6631  mov     rcx, rdi
0x1401d6634  call    TxfActOnAllStreamsForTransaction
0x1401d6639  mov     ebx, eax
0x1401d663b  mov     [rsp+178h+var_124], eax
0x1401d663f  test    eax, eax
0x1401d6641  jns     short loc_1401D66B0
0x1401d6643  cmp     eax, 0C0000017h
0x1401d6648  jz      loc_1401D6480
  ... truncated ...
```
