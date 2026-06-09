# RefsFsdClose(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x14033b510`
- end: `0x14033be19`
- name: `?RefsFsdClose@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `2313`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x14000b1b0`
- `0x14000e0e0`
- `0x140050ba0`
- `0x140075660`
- `0x1400862c0`
- `0x1400894e0`
- `0x14009a130`
- `0x1400a069c`
- `0x1400d0fd8`
- `0x1401f3fc0`
- `0x1403058c0`
- `0x14032d6c4`
- `0x1403348f4`
- `0x14033a7a8`
- `0x14033b510`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14033b8d4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14033bc37`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14033b8d4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14033bc37`
- `ntoskrnl!IofCompleteRequest` at `0x14033b58d`
- `ntoskrnl!IofCompleteRequest` at `0x14033b58d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14033b8b0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14033bc4e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14033b8b0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14033bc4e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14033b657`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14033b657`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14033b676`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14033b676`
- `ntoskrnl!IoClearActivityIdThread` at `0x14033bdd1`
- `ntoskrnl!IoClearActivityIdThread` at `0x14033bdd1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033bddd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033bddd`
- `ntoskrnl!IoGetCurrentProcess` at `0x14033b8e9`
- `ntoskrnl!IoGetCurrentProcess` at `0x14033b8e9`
- `ntoskrnl!KeQueryPriorityThread` at `0x14033b917`
- `ntoskrnl!KeQueryPriorityThread` at `0x14033b917`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14033bda7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14033bda7`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033b691`
- `ntoskrnl!KeEnterGuardedRegion` at `0x14033b691`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033b6a1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14033b6a1`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14033b7e4`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14033b7e4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033b6e3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033b6e3`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033b6ef`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033b6ef`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14033b9ef`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x14033b9ef`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14033bd12`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14033bd5f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14033bd12`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14033bd5f`

## pseudocode

```c
__int64 __fastcall RefsFsdClose(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PFILE_OBJECT FileObject; // rax
  _QWORD *FsContext; // rcx
  _QWORD *v6; // r15
  _BYTE *FsContext2; // rax
  __int64 v8; // r13
  char v9; // al
  __int64 v10; // rbx
  int v11; // eax
  PFILE_OBJECT v12; // rax
  struct _TOP_LEVEL_CONTEXT *v13; // rbx
  PFILE_OBJECT v14; // rdx
  __int16 v15; // cx
  unsigned int v16; // edi
  struct _IRP_CONTEXT *v17; // rsi
  struct _IRP_CONTEXT *v18; // rax
  unsigned int v19; // edx
  __int64 v20; // rbx
  PFILE_OBJECT v21; // rax
  PIRP TopLevelIrp; // rax
  unsigned __int8 v23; // si
  BOOLEAN *v24; // rdx
  __int64 v25; // rbx
  BOOLEAN *v26; // rbx
  _BYTE *v27; // r8
  __int64 v28; // r9
  int CompletionRoutine; // [rsp+20h] [rbp-108h]
  int PostIrpRoutine; // [rsp+28h] [rbp-100h]
  char v31; // [rsp+40h] [rbp-E8h]
  bool v32; // [rsp+41h] [rbp-E7h]
  __int64 v33; // [rsp+48h] [rbp-E0h]
  _BYTE *v34; // [rsp+50h] [rbp-D8h] BYREF
  struct _IRP_CONTEXT *v35; // [rsp+58h] [rbp-D0h] BYREF
  BOOLEAN *p_DeleteAccess; // [rsp+60h] [rbp-C8h] BYREF
  PFILE_OBJECT v37; // [rsp+68h] [rbp-C0h]
  int v38; // [rsp+70h] [rbp-B8h]
  struct _IRP *v39; // [rsp+78h] [rbp-B0h]
  __int64 v40; // [rsp+80h] [rbp-A8h]
  __int64 v41; // [rsp+88h] [rbp-A0h]
  _QWORD *v42; // [rsp+90h] [rbp-98h]
  _QWORD v43[5]; // [rsp+98h] [rbp-90h] BYREF
  PVOID *p_FsContext; // [rsp+C0h] [rbp-68h]
  BOOLEAN *p_WriteAccess; // [rsp+C8h] [rbp-60h]
  __int128 v46; // [rsp+D0h] [rbp-58h] BYREF
  __int64 v47; // [rsp+E0h] [rbp-48h]
  __int128 v48; // [rsp+E8h] [rbp-40h] BYREF

  v39 = a2;
  v46 = 0;
  v47 = 0;
  v35 = 0;
  v34 = 0;
  v48 = 0;
  v43[0] = 0;
  if ( *((_WORD *)a1 + 1) == 336 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v37 = FileObject;
  v43[3] = FileObject;
  p_FsContext = &FileObject->FsContext;
  FsContext = FileObject->FsContext;
  v42 = FsContext;
  v6 = FsContext;
  v43[2] = FsContext;
  if ( FsContext )
  {
    v33 = FsContext[18];
    v40 = v33;
    FsContext2 = FileObject->FsContext2;
    v34 = FsContext2;
    v8 = FsContext[17];
    v41 = v8;
    if ( FsContext2 )
      v9 = FsContext2[80];
    else
      v9 = 5;
  }
  else
  {
    v33 = 0;
    v40 = 0;
    v8 = 0;
    v41 = 0;
    v9 = 1;
  }
  v31 = v9;
  if ( v9 == 1 )
  {
    RefsCompleteRequest(0, a2, 0);
    return 0;
  }
  KeEnterCriticalRegion();
  v38 = IoPropagateActivityIdToThread(a2, &v48, v43);
  if ( v34 )
  {
    v10 = *(_QWORD *)(v8 + 88);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v10 + 8));
    *((_DWORD *)v34 + 1) |= 0x80000u;
    v11 = *((_DWORD *)v34 + 1);
    if ( (v11 & 0x10000000) != 0 )
    {
      *((_DWORD *)v34 + 1) = v11 | 0x4000;
      v12 = v37;
      v37->FileName.Buffer = 0;
      *(_DWORD *)&v12->FileName.Length = 0;
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v8 + 88) + 8LL));
    KeLeaveGuardedRegion();
  }
  v13 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v46, 0, 0);
  v43[1] = v13;
  v14 = v37;
  p_DeleteAccess = &v37->DeleteAccess;
  p_WriteAccess = &v37->WriteAccess;
  v32 = *(_WORD *)&v37->WriteAccess == 0;
  if ( v37->FileName.Buffer && !v37->FileName.Length )
    v37->FileName.Length = 1;
  if ( (v14->Flags & 0x4000) == 0 )
  {
    if ( ((v15 = *((_WORD *)v6 + 108), v15 == 128) || v15 == 176)
      && *(_WORD *)v6 == 2053
      && *(_QWORD **)(v6[18] + 72LL) != v6
      || v15 == 160
      && *((_WORD *)v6 + 112) == 8
      && *(_QWORD *)v6[29] == *(_QWORD *)RefsFileNameIndex.Buffer
      && (unsigned __int16)(*(_WORD *)v6 - 2051) <= 1u )
    {
      FsRtlCheckOplockEx((POPLOCK)v6 + 11, a2, 0, 0, 0, 0);
    }
  }
  if ( (int)RefsInitializeIrpContext(a2, 0, 0, &v35) >= 0 )
  {
    if ( *((_QWORD *)v13 + 2) )
    {
      v17 = v35;
    }
    else
    {
      *((_DWORD *)v13 + 1) = 1397140410;
      v17 = v35;
      *((_QWORD *)v13 + 2) = v35;
      *((_QWORD *)v17 + 1) |= 0x100000uLL;
      IoSetTopLevelIrp((PIRP)v13);
    }
    v18 = (struct _IRP_CONTEXT *)*((_QWORD *)v13 + 2);
    *((_QWORD *)v17 + 13) = v18;
    if ( v17 != v18 || !LOBYTE(IoGetTopLevelIrp()->Type) )
    {
      if ( !(unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(v6[17] + 88LL) + 64LL)
        || *(_DWORD *)(*((_QWORD *)v17 + 13) + 16LL) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids, 259);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(259, 0, "Close.c", 0x16Eu);
        v16 = 259;
        goto LABEL_73;
      }
      goto LABEL_62;
    }
    if ( IoGetCurrentProcess() != (PEPROCESS)qword_140268128 )
    {
      *((_QWORD *)v17 + 1) |= 1uLL;
LABEL_62:
      v20 = v33;
      goto LABEL_63;
    }
    ++RefsAsyncPassCount;
    if ( KeQueryPriorityThread(KeGetCurrentThread()) < 16 )
    {
      if ( (RefsAsyncPassCount & 3) == 0 )
        goto LABEL_62;
      v20 = v33;
      if ( 4 * *(_DWORD *)(v33 + 216) >= *(_DWORD *)(v33 + 220)
        || (v19 = *(_DWORD *)(v33 + 220) - *(_DWORD *)(v33 + 216),
            v19 <= RefsMaxDelayedCloseCount + RefsAsyncPostThreshold) )
      {
LABEL_63:
        RefsPreRequestProcessingExtend(v17, v19);
        if ( (v6[19] & 0x200000) == 0 || *(_DWORD *)(v6[17] + 208LL) )
        {
          LOBYTE(PostIrpRoutine) = v31;
          v16 = RefsCommonClose(v17, v6, v8, v20, &v34, PostIrpRoutine, v32, 0);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids, 259);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(259, 0, "Close.c", 0x189u);
          v16 = 259;
        }
        goto LABEL_73;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids, 259);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(259, 0, "Close.c", 0x15Eu);
    v16 = 259;
    goto LABEL_73;
  }
  _InterlockedIncrement((volatile signed __int32 *)&RefsFailedCloseIrpContextAllocations);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids, 259);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(259, 0, "Close.c", 0x12Eu);
  v16 = 259;
  v17 = v35;
LABEL_73:
  *p_FsContext = 0;
  v21 = v37;
  v37->FsContext2 = 0;
  v21->SectionObjectPointer = 0;
  if ( v16 == 259 )
  {
    if ( v17 && (*((_DWORD *)v17 + 2) & 0x100000) != 0 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
      *(_QWORD *)&TopLevelIrp->Flags = 0;
      IoSetTopLevelIrp((PIRP)TopLevelIrp->MdlAddress);
      *((_QWORD *)v17 + 1) &= ~0x100000uLL;
    }
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v17, a2, 0);
    v16 = 0;
    v23 = 0;
    if ( (v6[19] & 0x200000) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)v6 + 38, 0xFFDFFFFF);
      if ( !*(_DWORD *)(v6[17] + 208LL)
        && (v6[19] & 0x100) == 0
        && (*((__int16 *)v6 + 128) >= 0 || (*((_BYTE *)v42 + 4) & 0x20) == 0) )
      {
        v23 = 1;
      }
    }
    if ( v34 )
    {
      v24 = p_DeleteAccess;
      if ( *p_WriteAccess | *p_DeleteAccess )
      {
        *p_WriteAccess = 0;
        *v24 = 0;
        v25 = v33;
        _InterlockedIncrement((volatile signed __int32 *)(v33 + 224));
      }
      else
      {
        v25 = v33;
      }
      v26 = (BOOLEAN *)(v25 + 3504);
      ExAcquirePushLockExclusiveEx(v26, 0);
      p_DeleteAccess = v26;
      v27 = v34;
      v34[96] = 0;
      v27[90] = v23;
      *((_QWORD *)v27 + 16) = v6;
      CLOSE_QUEUE::QueueInternal(&p_DeleteAccess, v6, v27 + 104, v23);
    }
    else
    {
      v26 = (BOOLEAN *)(v33 + 3504);
      ExAcquirePushLockExclusiveEx(v33 + 3504, 0);
      p_DeleteAccess = (BOOLEAN *)(v33 + 3504);
      if ( !(unsigned __int8)CLOSE_QUEUE::QueueScb(&p_DeleteAccess, v6, v23) )
      {
        LOBYTE(CompletionRoutine) = 0;
        LOBYTE(v28) = 1;
        RefsDecrementCloseCounts(0, v6, 0, v28, CompletionRoutine, 3);
      }
    }
    ExReleasePushLockExclusiveEx(v26, 0);
  }
  else
  {
    RefsCompleteRequest(0, a2, v16);
  }
  if ( v38 >= 0 )
    IoClearActivityIdThread(v43[0]);
  KeLeaveCriticalRegion();
  return v16;
}

```

## disassembly

```asm
0x14033b510  mov     r11, rsp
0x14033b513  mov     [r11+8], rbx
0x14033b517  mov     [r11+18h], rsi
0x14033b51b  push    rdi
0x14033b51c  push    r12
0x14033b51e  push    r13
0x14033b520  push    r14
0x14033b522  push    r15
0x14033b524  sub     rsp, 100h
0x14033b52b  mov     rax, cs:__security_cookie
0x14033b532  xor     rax, rsp
0x14033b535  mov     [rsp+128h+var_30], rax
0x14033b53d  mov     r14, rdx
0x14033b540  mov     [rsp+128h+var_B0], rdx
0x14033b545  xorps   xmm0, xmm0
0x14033b548  xor     eax, eax
0x14033b54a  movups  xmmword ptr [r11-58h], xmm0
0x14033b54f  mov     [r11-48h], rax
0x14033b553  xor     r12d, r12d
0x14033b556  mov     esi, r12d
0x14033b559  mov     [rsp+128h+var_D0], r12
0x14033b55e  mov     [rsp+128h+var_D8], r12
0x14033b563  movups  xmmword ptr [r11-40h], xmm0
0x14033b568  mov     [r11-90h], r12
0x14033b56f  mov     eax, 150h
0x14033b574  cmp     [rcx+2], ax
0x14033b578  jnz     short loc_14033B5A0
0x14033b57a  mov     [rdx+30h], r12d
0x14033b57e  mov     eax, 1
0x14033b583  mov     [rdx+38h], rax
0x14033b587  movzx   edx, al; PriorityBoost
0x14033b58a  mov     rcx, r14; Irp
0x14033b58d  call    cs:__imp_IofCompleteRequest
0x14033b594  nop     dword ptr [rax+rax+00h]
0x14033b599  xor     eax, eax
0x14033b59b  jmp     loc_14033BDEB
0x14033b5a0  mov     rax, [rdx+0B8h]
0x14033b5a7  mov     rax, [rax+30h]
0x14033b5ab  mov     [rsp+128h+var_C0], rax
0x14033b5b0  mov     [rsp+128h+var_78], rax
0x14033b5b8  lea     rcx, [rax+18h]
0x14033b5bc  mov     [rsp+128h+var_68], rcx
0x14033b5c4  mov     rcx, [rcx]
0x14033b5c7  mov     [rsp+128h+var_98], rcx
0x14033b5cf  mov     r15, rcx
0x14033b5d2  mov     [rsp+128h+var_80], rcx
0x14033b5da  test    rcx, rcx
0x14033b5dd  jz      short loc_14033B61A
0x14033b5df  mov     rbx, [rcx+90h]
0x14033b5e6  mov     [rsp+128h+var_E0], rbx
0x14033b5eb  mov     [rsp+128h+var_A8], rbx
0x14033b5f3  mov     rax, [rax+20h]
0x14033b5f7  mov     [rsp+128h+var_D8], rax
0x14033b5fc  mov     r13, [rcx+88h]
0x14033b603  mov     [rsp+128h+var_A0], r13
0x14033b60b  test    rax, rax
0x14033b60e  jnz     short loc_14033B614
0x14033b610  mov     al, 5
0x14033b612  jmp     short loc_14033B637
0x14033b614  movzx   eax, byte ptr [rax+50h]
0x14033b618  jmp     short loc_14033B637
0x14033b61a  mov     rbx, r12
0x14033b61d  mov     [rsp+128h+var_E0], rbx
0x14033b622  mov     [rsp+128h+var_A8], rbx
0x14033b62a  mov     r13, r12
0x14033b62d  mov     [rsp+128h+var_A0], r12
0x14033b635  mov     al, 1
0x14033b637  mov     [rsp+128h+var_E8], al
0x14033b63b  cmp     al, 1
0x14033b63d  jnz     short loc_14033B650
0x14033b63f  xor     r8d, r8d; Status
0x14033b642  xor     ecx, ecx; struct _IRP_CONTEXT *
0x14033b644  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14033b649  xor     eax, eax
0x14033b64b  jmp     loc_14033BDEB
0x14033b650  mov     [rsp+128h+var_E6], al
0x14033b654  mov     edi, r12d
0x14033b657  call    cs:__imp_KeEnterCriticalRegion
0x14033b65e  nop     dword ptr [rax+rax+00h]
0x14033b663  lea     r8, [rsp+128h+var_90]
0x14033b66b  lea     rdx, [rsp+128h+var_40]
0x14033b673  mov     rcx, r14
0x14033b676  call    cs:__imp_IoPropagateActivityIdToThread
0x14033b67d  nop     dword ptr [rax+rax+00h]
0x14033b682  mov     [rsp+128h+var_B8], eax
0x14033b686  cmp     [rsp+128h+var_D8], r12
0x14033b68b  jz      short loc_14033B6FB
0x14033b68d  mov     rbx, [r13+58h]
0x14033b691  call    cs:__imp_KeEnterGuardedRegion
0x14033b698  nop     dword ptr [rax+rax+00h]
0x14033b69d  lea     rcx, [rbx+8]; FastMutex
0x14033b6a1  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14033b6a8  nop     dword ptr [rax+rax+00h]
0x14033b6ad  mov     rax, [rsp+128h+var_D8]
0x14033b6b2  or      dword ptr [rax+4], 80000h
0x14033b6b9  mov     rcx, [rsp+128h+var_D8]
0x14033b6be  mov     eax, [rcx+4]
0x14033b6c1  bt      eax, 1Ch
0x14033b6c5  jnb     short loc_14033B6DB
0x14033b6c7  bts     eax, 0Eh
0x14033b6cb  mov     [rcx+4], eax
0x14033b6ce  mov     rax, [rsp+128h+var_C0]
0x14033b6d3  mov     [rax+60h], r12
0x14033b6d7  mov     [rax+58h], r12d
0x14033b6db  mov     rcx, [r13+58h]
0x14033b6df  add     rcx, 8; FastMutex
0x14033b6e3  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14033b6ea  nop     dword ptr [rax+rax+00h]
0x14033b6ef  call    cs:__imp_KeLeaveGuardedRegion
0x14033b6f6  nop     dword ptr [rax+rax+00h]
0x14033b6fb  xor     r8d, r8d; unsigned __int8
0x14033b6fe  xor     edx, edx; unsigned __int8
0x14033b700  lea     rcx, [rsp+128h+var_58]; struct _TOP_LEVEL_CONTEXT *
0x14033b708  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x14033b70d  mov     rbx, rax
0x14033b710  mov     [rsp+128h+var_88], rax
0x14033b718  mov     rdx, [rsp+128h+var_C0]
0x14033b71d  lea     rax, [rdx+4Ch]
0x14033b721  mov     [rsp+128h+var_C8], rax
0x14033b726  lea     rcx, [rdx+4Bh]
0x14033b72a  mov     [rsp+128h+var_60], rcx
0x14033b732  movzx   eax, byte ptr [rax]
0x14033b735  or      al, [rcx]
0x14033b737  setz    [rsp+128h+var_E7]
0x14033b73c  cmp     [rdx+60h], r12
0x14033b740  jz      short loc_14033B74F
0x14033b742  cmp     [rdx+58h], r12w
0x14033b747  jnz     short loc_14033B74F
0x14033b749  mov     word ptr [rdx+58h], 1
0x14033b74f  mov     eax, [rdx+50h]
0x14033b752  bt      eax, 0Eh
0x14033b756  jb      loc_14033B7F0
0x14033b75c  movzx   ecx, word ptr [r15+0D8h]
0x14033b764  mov     eax, 80h
0x14033b769  cmp     cx, ax
0x14033b76c  jz      short loc_14033B778
0x14033b76e  mov     eax, 0B0h
0x14033b773  cmp     cx, ax
0x14033b776  jnz     short loc_14033B790
0x14033b778  mov     eax, 805h
0x14033b77d  cmp     [r15], ax
0x14033b781  jnz     short loc_14033B790
0x14033b783  mov     rax, [r15+90h]
0x14033b78a  cmp     [rax+48h], r15
0x14033b78e  jnz     short loc_14033B7CD
0x14033b790  mov     eax, 0A0h
0x14033b795  cmp     cx, ax
0x14033b798  jnz     short loc_14033B7F0
0x14033b79a  cmp     word ptr [r15+0E0h], 8
0x14033b7a3  jnz     short loc_14033B7F0
0x14033b7a5  mov     rax, [r15+0E8h]
0x14033b7ac  mov     rcx, cs:?RefsFileNameIndex@@3U_UNICODE_STRING@@B.Buffer; _UNICODE_STRING const RefsFileNameIndex ...
0x14033b7b3  mov     rax, [rax]
0x14033b7b6  cmp     rax, [rcx]
0x14033b7b9  jnz     short loc_14033B7F0
0x14033b7bb  mov     ecx, 803h
0x14033b7c0  movzx   eax, word ptr [r15]
0x14033b7c4  sub     ax, cx
0x14033b7c7  cmp     ax, 1
0x14033b7cb  ja      short loc_14033B7F0
0x14033b7cd  lea     rcx, [r15+58h]; Oplock
0x14033b7d1  mov     [rsp+128h+PostIrpRoutine], r12; PostIrpRoutine
0x14033b7d6  mov     [rsp+128h+CompletionRoutine], r12; CompletionRoutine
0x14033b7db  xor     r9d, r9d; Context
0x14033b7de  xor     r8d, r8d; Flags
0x14033b7e1  mov     rdx, r14; Irp
0x14033b7e4  call    cs:__imp_FsRtlCheckOplockEx
0x14033b7eb  nop     dword ptr [rax+rax+00h]
0x14033b7f0  lea     r12, WPP_GLOBAL_Control
0x14033b7f7  test    rsi, rsi
0x14033b7fa  jnz     loc_14033BA71
0x14033b800  lea     r9, [rsp+128h+var_D0]; struct _IRP_CONTEXT **
0x14033b805  xor     r8d, r8d; unsigned __int8
0x14033b808  xor     edx, edx; unsigned __int8
0x14033b80a  mov     rcx, r14; Irp
0x14033b80d  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x14033b812  mov     [rsp+128h+var_E4], eax
0x14033b816  test    eax, eax
0x14033b818  jns     short loc_14033B88E
0x14033b81a  lock inc cs:?RefsFailedCloseIrpContextAllocations@@3KA; ulong RefsFailedCloseIrpContextAllocations
0x14033b821  mov     rcx, cs:WPP_GLOBAL_Control
0x14033b828  cmp     rcx, r12
0x14033b82b  jz      short loc_14033B857
0x14033b82d  test    dword ptr [rcx+2Ch], 100h
0x14033b834  jz      short loc_14033B857
0x14033b836  cmp     byte ptr [rcx+29h], 5
0x14033b83a  jb      short loc_14033B857
0x14033b83c  mov     edx, 0Ah
0x14033b841  mov     r9d, 103h
0x14033b847  lea     r8, WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids
0x14033b84e  mov     rcx, [rcx+18h]
0x14033b852  call    WPP_SF_d
0x14033b857  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14033b85e  test    al, al
0x14033b860  jz      short loc_14033B87B
0x14033b862  mov     r9d, 12Eh; unsigned int
0x14033b868  lea     r8, aCloseC; "Close.c"
0x14033b86f  xor     edx, edx; struct _IRP_CONTEXT *
0x14033b871  mov     ecx, 103h; Status
0x14033b876  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14033b87b  mov     edi, 103h
0x14033b880  mov     [rsp+128h+var_E4], edi
0x14033b884  mov     rsi, [rsp+128h+var_D0]
0x14033b889  jmp     loc_14033BBDE
0x14033b88e  cmp     qword ptr [rbx+10h], 0
0x14033b893  jnz     short loc_14033B8BE
0x14033b895  mov     dword ptr [rbx+4], 5346ABBAh
0x14033b89c  mov     rsi, [rsp+128h+var_D0]
0x14033b8a1  mov     [rbx+10h], rsi
0x14033b8a5  or      qword ptr [rsi+8], 100000h
0x14033b8ad  mov     rcx, rbx; Irp
0x14033b8b0  call    cs:__imp_IoSetTopLevelIrp
0x14033b8b7  nop     dword ptr [rax+rax+00h]
0x14033b8bc  jmp     short loc_14033B8C3
0x14033b8be  mov     rsi, [rsp+128h+var_D0]
0x14033b8c3  mov     rax, [rbx+10h]
0x14033b8c7  mov     [rsi+68h], rax
0x14033b8cb  cmp     rsi, rax
0x14033b8ce  jnz     loc_14033B9E0
0x14033b8d4  call    cs:__imp_IoGetTopLevelIrp
0x14033b8db  nop     dword ptr [rax+rax+00h]
0x14033b8e0  cmp     byte ptr [rax], 0
0x14033b8e3  jz      loc_14033B9E0
0x14033b8e9  call    cs:__imp_IoGetCurrentProcess
0x14033b8f0  nop     dword ptr [rax+rax+00h]
0x14033b8f5  cmp     rax, cs:qword_140268128
0x14033b8fc  jz      short loc_14033B908
0x14033b8fe  or      qword ptr [rsi+8], 1
0x14033b903  jmp     loc_14033BA81
0x14033b908  inc     cs:?RefsAsyncPassCount@@3KA; ulong RefsAsyncPassCount
0x14033b90e  mov     rcx, gs:188h; Thread
0x14033b917  call    cs:__imp_KeQueryPriorityThread
0x14033b91e  nop     dword ptr [rax+rax+00h]
0x14033b923  cmp     eax, 10h
0x14033b926  jge     short loc_14033B978
0x14033b928  mov     eax, cs:?RefsAsyncPassCount@@3KA; ulong RefsAsyncPassCount
0x14033b92e  test    al, 3
0x14033b930  jz      loc_14033BA81
0x14033b936  mov     rbx, [rsp+128h+var_E0]
0x14033b93b  mov     eax, [rbx+0D8h]
0x14033b941  mov     ecx, [rbx+0DCh]
0x14033b947  lea     eax, ds:0[rax*4]
0x14033b94e  cmp     eax, ecx
0x14033b950  jge     loc_14033BA86
0x14033b956  mov     edx, [rbx+0DCh]
0x14033b95c  mov     eax, [rbx+0D8h]
0x14033b962  sub     edx, eax
0x14033b964  mov     ecx, cs:?RefsAsyncPostThreshold@@3KA; ulong RefsAsyncPostThreshold
0x14033b96a  add     ecx, cs:?RefsMaxDelayedCloseCount@@3KA; ulong RefsMaxDelayedCloseCount
0x14033b970  cmp     edx, ecx
0x14033b972  jbe     loc_14033BA86
0x14033b978  mov     rcx, cs:WPP_GLOBAL_Control
0x14033b97f  cmp     rcx, r12
0x14033b982  jz      short loc_14033B9AE
0x14033b984  test    dword ptr [rcx+2Ch], 100h
0x14033b98b  jz      short loc_14033B9AE
0x14033b98d  cmp     byte ptr [rcx+29h], 5
0x14033b991  jb      short loc_14033B9AE
0x14033b993  mov     edx, 0Bh
0x14033b998  mov     r9d, 103h
0x14033b99e  lea     r8, WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids
0x14033b9a5  mov     rcx, [rcx+18h]
0x14033b9a9  call    WPP_SF_d
0x14033b9ae  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14033b9b5  test    al, al
0x14033b9b7  jz      short loc_14033B9D2
0x14033b9b9  mov     r9d, 15Eh; unsigned int
0x14033b9bf  lea     r8, aCloseC; "Close.c"
0x14033b9c6  xor     edx, edx; struct _IRP_CONTEXT *
0x14033b9c8  mov     ecx, 103h; Status
0x14033b9cd  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14033b9d2  mov     edi, 103h
0x14033b9d7  mov     [rsp+128h+var_E4], edi
0x14033b9db  jmp     loc_14033BC02
0x14033b9e0  mov     rax, [r15+88h]
0x14033b9e7  mov     rcx, [rax+58h]
0x14033b9eb  add     rcx, 40h ; '@'
0x14033b9ef  call    cs:__imp_ExIsFastResourceHeldExclusive
0x14033b9f6  nop     dword ptr [rax+rax+00h]
0x14033b9fb  test    al, al
0x14033b9fd  jz      short loc_14033BA09
0x14033b9ff  mov     rax, [rsi+68h]
0x14033ba03  cmp     dword ptr [rax+10h], 0
0x14033ba07  jz      short loc_14033BA81
0x14033ba09  mov     rcx, cs:WPP_GLOBAL_Control
0x14033ba10  cmp     rcx, r12
0x14033ba13  jz      short loc_14033BA3F
0x14033ba15  test    dword ptr [rcx+2Ch], 100h
0x14033ba1c  jz      short loc_14033BA3F
0x14033ba1e  cmp     byte ptr [rcx+29h], 5
0x14033ba22  jb      short loc_14033BA3F
0x14033ba24  mov     edx, 0Ch
0x14033ba29  mov     r9d, 103h
0x14033ba2f  lea     r8, WPP_1c85bb5b66a232ec1db5ccda4cda7290_Traceguids
0x14033ba36  mov     rcx, [rcx+18h]
0x14033ba3a  call    WPP_SF_d
0x14033ba3f  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14033ba46  test    al, al
0x14033ba48  jz      short loc_14033BA63
0x14033ba4a  mov     r9d, 16Eh; unsigned int
  ... truncated ...
```
