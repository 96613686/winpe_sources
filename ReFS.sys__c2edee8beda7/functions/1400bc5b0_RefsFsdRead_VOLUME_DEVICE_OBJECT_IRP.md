# RefsFsdRead(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400bc5b0`
- end: `0x1400bce86`
- name: `?RefsFsdRead@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `2262`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000b1b0`
- `0x14000dfe0`
- `0x14000e0e0`
- `0x140038480`
- `0x140050ff0`
- `0x140075660`
- `0x1400862c0`
- `0x1400892a0`
- `0x140097d10`
- `0x14009a130`
- `0x1400a01b0`
- `0x1400a069c`
- `0x1400ba4d0`
- `0x1400bc5b0`
- `0x1400d0fd8`
- `0x1400ef254`
- `0x1400ffb3c`
- `0x1401f3fc0`
- `0x14032c7c0`
- `0x14033a7a8`
- `0x14033aca8`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1400bcc38`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400bcc38`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400bc741`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400bcc18`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400bcc50`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400bc741`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400bcc18`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400bcc50`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bc977`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bcbef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bc977`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bcbef`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400bc98e`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400bc98e`
- `ntoskrnl!IoGetStackLimits` at `0x1400bca6b`
- `ntoskrnl!IoGetStackLimits` at `0x1400bca6b`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400bcbc8`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400bcbc8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bcbd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bcc64`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bcbd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bcc64`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bc8a0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bc8ba`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bcdbc`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bcdd6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bc8a0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bc8ba`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bcdbc`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bcdd6`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400bc6d7`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400bc6d7`
- `ntoskrnl!DbgPrintEx` at `0x1400bc83a`
- `ntoskrnl!DbgPrintEx` at `0x1400bcd56`
- `ntoskrnl!DbgPrintEx` at `0x1400bc83a`
- `ntoskrnl!DbgPrintEx` at `0x1400bcd56`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bc866`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bcd82`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bc866`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bcd82`
- `ntoskrnl!_strnicmp` at `0x1400bc8e5`
- `ntoskrnl!_strnicmp` at `0x1400bce01`
- `ntoskrnl!_strnicmp` at `0x1400bc8e5`
- `ntoskrnl!_strnicmp` at `0x1400bce01`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bc8c9`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bcde5`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bc8c9`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bcde5`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bc9dc`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bcbaa`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bc9dc`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bcbaa`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x1400bca00`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x1400bca00`
- `HAL!KeQueryPerformanceCounter` at `0x1400bc9b1`
- `HAL!KeQueryPerformanceCounter` at `0x1400bc9b1`

## string_xrefs

- `0x1400bc804`: `Read.c`
- `0x1400bcb15`: `Read.c`
- `0x1400bcd20`: `Read.c`

## pseudocode

```c
__int64 __fastcall RefsFsdRead(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  PFILE_OBJECT FileObject; // rdx
  char v4; // cl
  struct _SCB *FsContext; // r14
  _BYTE *FsContext2; // rcx
  __int64 v7; // rcx
  __int64 v8; // r13
  struct _TOP_LEVEL_CONTEXT *v9; // rdi
  void *v10; // rsp
  char *NPagedPerProcessorLookaside; // rbx
  bool v12; // r12
  struct REFS_IO_CONTEXT *v13; // r13
  __int64 v14; // rax
  __int64 v15; // rcx
  volatile unsigned int v17; // edi
  struct _KPROCESS *v18; // rdi
  PEPROCESS v19; // rax
  const char *v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // edi
  int v23; // r12d
  __int64 v24; // r14
  int v25; // edx
  bool v26; // r8
  unsigned int v27; // eax
  IRP *v28; // r8
  struct REFS_IO_CONTEXT *v29; // rdx
  struct _IRP_CONTEXT *v30; // rcx
  PIRP TopLevelIrp; // rax
  volatile unsigned int v32; // edi
  struct _KPROCESS *v33; // rdi
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  __int64 v36; // rdx
  char v37; // [rsp+0h] [rbp-680h] BYREF
  unsigned int v38; // [rsp+680h] [rbp+0h]
  int v39; // [rsp+684h] [rbp+4h]
  int v40; // [rsp+688h] [rbp+8h]
  _QWORD v41[2]; // [rsp+690h] [rbp+10h] BYREF
  __int64 v42; // [rsp+6A0h] [rbp+20h]
  unsigned __int64 HighLimit; // [rsp+6A8h] [rbp+28h] BYREF
  unsigned __int64 LowLimit[2]; // [rsp+6B0h] [rbp+30h] BYREF
  __int64 *v45; // [rsp+6C0h] [rbp+40h]
  _QWORD v46[3]; // [rsp+6C8h] [rbp+48h] BYREF
  __int128 v47; // [rsp+6E0h] [rbp+60h] BYREF
  __int64 v48; // [rsp+6F0h] [rbp+70h]
  __int128 v49; // [rsp+6F8h] [rbp+78h] BYREF

  LowLimit[1] = (unsigned __int64)a2;
  v47 = 0;
  v48 = 0;
  v41[0] = 0;
  v49 = 0;
  v46[0] = 0;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  v4 = 1;
  FsContext = (struct _SCB *)FileObject->FsContext;
  if ( FsContext )
  {
    FsContext2 = FileObject->FsContext2;
    if ( !FsContext2 )
      goto LABEL_6;
    v4 = FsContext2[80];
  }
  if ( ((v4 - 2) & 0xFC) != 0 || v4 == 3 )
  {
LABEL_77:
    RefsCompleteRequest(0, a2, -1073741808);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids, 3221225488LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741808 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741808, "Read.c", 136);
      v32 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741808
        || RefsStatusBreakOnWin32Error && v32 == RtlNtStatusToDosErrorNoTeb(-1073741808) )
      {
        v33 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v33 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (CurrentProcess = IoGetCurrentProcess(),
               ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
               !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu))) )
        {
          __int2c();
        }
      }
      v36 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(_QWORD *)((char *)&RefsStatusQueue + v36) = KeGetCurrentThread();
      *(unsigned int *)((char *)&RefsStatusQueue + v36 + 8) = -1073741808;
      *(_QWORD *)((char *)&RefsStatusQueue + v36 + 16) = "Read.c";
      *(unsigned int *)((char *)&RefsStatusQueue + v36 + 24) = 136;
    }
    return 3221225488LL;
  }
LABEL_6:
  v7 = *(_QWORD *)(*((_QWORD *)FsContext + 17) + 88LL);
  if ( *(_QWORD *)(v7 + 256) == 1313 && *(_QWORD *)(v7 + 248) == 1024 || !FsContext )
    goto LABEL_77;
  v8 = MsCaptureTopLevelContext();
  v42 = v8;
  v9 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v47, 0, 0);
  if ( ((*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 4) != 0
     || (*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 0x8000LL) != 0)
    && ((*(_QWORD *)(*((_QWORD *)FsContext + 17) + 8LL) & 4) != 0 && (*((_DWORD *)FsContext + 38) & 0x10) != 0
     || *(struct _SCB **)(*((_QWORD *)FsContext + 18) + 40LL) == FsContext) )
  {
    KeEnterCriticalRegion();
    if ( v9 == (struct _TOP_LEVEL_CONTEXT *)&v47 && !*((_QWORD *)v9 + 2) )
    {
      *((_DWORD *)v9 + 1) = 1397140410;
      *((_QWORD *)v9 + 2) = 0;
      IoSetTopLevelIrp((PIRP)v9);
    }
    RefsPagingFileIo(a2, FsContext);
    if ( v9 == (struct _TOP_LEVEL_CONTEXT *)&v47 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
      *(_QWORD *)&TopLevelIrp->Flags = 0;
      IoSetTopLevelIrp((PIRP)TopLevelIrp->MdlAddress);
    }
    MsRestoreTopLevelContext(v8);
    KeLeaveCriticalRegion();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids, 259);
    }
    return 259;
  }
  else
  {
    if ( IoIsOperationSynchronous(a2) && (a2->Flags & 2) != 0 )
    {
      v10 = alloca(1664);
      NPagedPerProcessorLookaside = &v37;
      v12 = 1;
LABEL_17:
      RefsInitializeIrpAndIoContext(a2, (struct IRP_AND_IO_CONTEXT *)NPagedPerProcessorLookaside, v12);
      v13 = (struct REFS_IO_CONTEXT *)(NPagedPerProcessorLookaside + 800);
      v46[1] = NPagedPerProcessorLookaside + 800;
      if ( !*((_QWORD *)v9 + 2) )
      {
        *((_DWORD *)v9 + 1) = 1397140410;
        *((_QWORD *)v9 + 2) = NPagedPerProcessorLookaside;
        *((_QWORD *)NPagedPerProcessorLookaside + 1) |= 0x100000uLL;
        IoSetTopLevelIrp((PIRP)v9);
      }
      v14 = *((_QWORD *)v9 + 2);
      *((_QWORD *)NPagedPerProcessorLookaside + 13) = v14;
      v45 = (__int64 *)(NPagedPerProcessorLookaside + 672);
      v15 = v42;
      *((_QWORD *)NPagedPerProcessorLookaside + 84) = v42;
      if ( *(_QWORD *)(v14 + 344) )
      {
        MsRestoreTopLevelContext(v15);
        RefsCompleteReadWriteRequest(
          (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside,
          (struct REFS_IO_CONTEXT *)(NPagedPerProcessorLookaside + 800),
          a2,
          -1073739768);
        return 3221227528LL;
      }
      v41[1] = NPagedPerProcessorLookaside;
      v46[2] = NPagedPerProcessorLookaside + 672;
      v22 = 0;
      v23 = 0;
      v40 = 0;
      KeEnterCriticalRegion();
      v39 = IoPropagateActivityIdToThread(a2, &v49, v46);
      if ( *(_BYTE *)(*((_QWORD *)FsContext + 18) + 10304LL) )
        *((LARGE_INTEGER *)NPagedPerProcessorLookaside + 86) = KeQueryPerformanceCounter(0);
      v24 = v42;
      while ( 1 )
      {
        if ( v22 == -1073741432 )
        {
          RefsCheckpointForLogFileFull((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside);
        }
        else if ( (unsigned __int8)CcIsCacheManagerCallbackNeeded(v22) )
        {
          LODWORD(v41[0]) = 8;
          HIDWORD(v41[0]) = v22;
          CcErrorCallbackRoutine(v41);
        }
        if ( !NPagedPerProcessorLookaside )
          goto LABEL_59;
        if ( v23 )
          RefsInitializeIoContext((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v13, v26, (a2->Flags & 2) != 0);
        RefsPreRequestProcessingExtend((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v25);
        *v45 = v24;
        if ( (NPagedPerProcessorLookaside[41] & 4) != 0 )
        {
          v27 = RefsCompleteMdl((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, a2);
        }
        else
        {
          if ( !RefsFeature_Servicing_ReFSStackSwapRead_IsEnabled )
          {
            v28 = a2;
            v29 = (struct REFS_IO_CONTEXT *)(NPagedPerProcessorLookaside + 800);
            v30 = (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside;
LABEL_57:
            v27 = RefsCommonRead(v30, v29, v28);
            goto LABEL_58;
          }
          HighLimit = 0;
          LowLimit[0] = 0;
          IoGetStackLimits(LowLimit, &HighLimit);
          v28 = a2;
          v29 = (struct REFS_IO_CONTEXT *)(NPagedPerProcessorLookaside + 800);
          v30 = (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside;
          if ( (unsigned __int64)&LowLimit[-1] - LowLimit[0] > 0x3000 )
            goto LABEL_57;
          v27 = RefsCommonIoOnNewStack((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v13, a2);
        }
LABEL_58:
        v38 = v27;
        v22 = v27;
LABEL_59:
        if ( v22 )
        {
          v40 = ++v23;
          if ( v22 == -1073741608
            || v22 == -1073741400
            || v22 == -1073741432
            || (unsigned __int8)CcIsCacheManagerCallbackNeeded(v22) )
          {
            continue;
          }
        }
        if ( v39 >= 0 )
          IoClearActivityIdThread(v46[0]);
        KeLeaveCriticalRegion();
        MsRestoreTopLevelContext(v24);
        return v22;
      }
    }
    v12 = 0;
    NPagedPerProcessorLookaside = (char *)RefsAllocateNPagedPerProcessorLookaside(RefsIrpAndIoContextLookasideList);
    if ( NPagedPerProcessorLookaside )
      goto LABEL_17;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids, 3221225626LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      if ( RefsStatusDisplayStatus == -1073741670 )
        DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741670, "Read.c", 167);
      v17 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnStatus == -1073741670
        || RefsStatusBreakOnWin32Error && v17 == RtlNtStatusToDosErrorNoTeb(-1073741670) )
      {
        v18 = RefsStatusBreakForProcess;
        if ( !RefsStatusBreakForThread
          || RefsStatusBreakForThread == KeGetCurrentThread()
          && (!RefsStatusBreakForProcess || v18 == IoGetCurrentProcess())
          && (!RefsStatusBreakForImage
           || (v19 = IoGetCurrentProcess(),
               v20 = (const char *)PsGetProcessImageFileName(v19),
               !_strnicmp(&RefsStatusBreakForImage, v20, 0xFu))) )
        {
          __int2c();
        }
      }
      v21 = 32LL
          * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
           & 0xFFF);
      *(_QWORD *)((char *)&RefsStatusQueue + v21) = KeGetCurrentThread();
      *(unsigned int *)((char *)&RefsStatusQueue + v21 + 8) = -1073741670;
      *(_QWORD *)((char *)&RefsStatusQueue + v21 + 16) = "Read.c";
      *(unsigned int *)((char *)&RefsStatusQueue + v21 + 24) = 167;
    }
    MsRestoreTopLevelContext(v8);
    RefsCompleteReadWriteRequest(0, 0, a2, -1073741670);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400bc5b0  push    rbp
0x1400bc5b2  push    rbx
0x1400bc5b3  push    rsi
0x1400bc5b4  push    rdi
0x1400bc5b5  push    r12
0x1400bc5b7  push    r13
0x1400bc5b9  push    r14
0x1400bc5bb  push    r15
0x1400bc5bd  sub     rsp, 0D8h
0x1400bc5c4  lea     rbp, [rsp+40h]
0x1400bc5c9  mov     rax, cs:__security_cookie
0x1400bc5d0  xor     rax, rbp
0x1400bc5d3  mov     [rbp+0D0h+var_48], rax
0x1400bc5da  mov     rsi, rdx
0x1400bc5dd  mov     [rbp+0D0h+var_98], rdx
0x1400bc5e1  xorps   xmm0, xmm0
0x1400bc5e4  xor     eax, eax
0x1400bc5e6  movups  [rbp+0D0h+var_70], xmm0
0x1400bc5ea  mov     [rbp+0D0h+var_60], rax
0x1400bc5ee  xor     r15d, r15d
0x1400bc5f1  mov     [rbp+0D0h+var_C0], r15
0x1400bc5f5  movups  [rbp+0D0h+var_58], xmm0
0x1400bc5f9  mov     [rbp+0D0h+var_88], r15
0x1400bc5fd  mov     rax, [rdx+0B8h]
0x1400bc604  mov     rdx, [rax+30h]
0x1400bc608  mov     cl, 1
0x1400bc60a  mov     r14, [rdx+18h]
0x1400bc60e  test    r14, r14
0x1400bc611  jz      short loc_1400BC620
0x1400bc613  mov     rcx, [rdx+20h]
0x1400bc617  test    rcx, rcx
0x1400bc61a  jz      short loc_1400BC634
0x1400bc61c  movzx   ecx, byte ptr [rcx+50h]
0x1400bc620  lea     eax, [rcx-2]
0x1400bc623  test    al, 0FCh
0x1400bc625  jnz     loc_1400BCCBE
0x1400bc62b  cmp     cl, 3
0x1400bc62e  jz      loc_1400BCCBE
0x1400bc634  mov     rax, [r14+88h]
0x1400bc63b  mov     rcx, [rax+58h]
0x1400bc63f  cmp     qword ptr [rcx+100h], 521h
0x1400bc64a  jnz     short loc_1400BC65D
0x1400bc64c  cmp     qword ptr [rcx+0F8h], 400h
0x1400bc657  jz      loc_1400BCCBE
0x1400bc65d  test    r14, r14
0x1400bc660  jz      loc_1400BCCBE
0x1400bc666  call    MsCaptureTopLevelContext
0x1400bc66b  mov     r13, rax
0x1400bc66e  mov     [rbp+0D0h+var_B0], rax
0x1400bc672  xor     r8d, r8d; unsigned __int8
0x1400bc675  xor     edx, edx; unsigned __int8
0x1400bc677  lea     rcx, [rbp+0D0h+var_70]; struct _TOP_LEVEL_CONTEXT *
0x1400bc67b  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x1400bc680  mov     rdi, rax
0x1400bc683  mov     rcx, [r14+88h]
0x1400bc68a  mov     rdx, [rcx+8]
0x1400bc68e  test    dl, 4
0x1400bc691  jnz     short loc_1400BC6A5
0x1400bc693  mov     rcx, [r14+88h]
0x1400bc69a  mov     rdx, [rcx+8]
0x1400bc69e  bt      rdx, 0Fh
0x1400bc6a3  jnb     short loc_1400BC6D4
0x1400bc6a5  mov     rcx, [r14+88h]
0x1400bc6ac  mov     rax, [rcx+8]
0x1400bc6b0  test    al, 4
0x1400bc6b2  jz      short loc_1400BC6C3
0x1400bc6b4  mov     eax, [r14+98h]
0x1400bc6bb  test    al, 10h
0x1400bc6bd  jnz     loc_1400BCBEF
0x1400bc6c3  mov     rax, [r14+90h]
0x1400bc6ca  cmp     [rax+28h], r14
0x1400bc6ce  jz      loc_1400BCBEF
0x1400bc6d4  mov     rcx, rsi; Irp
0x1400bc6d7  call    cs:__imp_IoIsOperationSynchronous
0x1400bc6de  nop     dword ptr [rax+rax+00h]
0x1400bc6e3  test    al, al
0x1400bc6e5  jz      loc_1400BC797
0x1400bc6eb  mov     eax, [rsi+10h]
0x1400bc6ee  test    al, 2
0x1400bc6f0  jz      loc_1400BC797
0x1400bc6f6  mov     eax, [rsp+110h+var_110]
0x1400bc6f9  mov     eax, 680h
0x1400bc6fe  sub     rsp, rax
0x1400bc701  lea     rbx, [rsp+790h+var_750]
0x1400bc706  mov     eax, [rbx]
0x1400bc708  mov     r12b, 1
0x1400bc70b  movzx   r8d, r12b; bool
0x1400bc70f  mov     rdx, rbx; struct IRP_AND_IO_CONTEXT *
0x1400bc712  mov     rcx, rsi; Irp
0x1400bc715  call    ?RefsInitializeIrpAndIoContext@@YAXPEAU_IRP@@PEAUIRP_AND_IO_CONTEXT@@_N@Z; RefsInitializeIrpAndIoContext(_IRP *,IRP_AND_IO_CONTEXT *,bool)
0x1400bc71a  lea     r13, [rbx+320h]
0x1400bc721  mov     [rbp+0D0h+var_80], r13
0x1400bc725  cmp     [rdi+10h], r15
0x1400bc729  jnz     short loc_1400BC74D
0x1400bc72b  mov     dword ptr [rdi+4], 5346ABBAh
0x1400bc732  mov     [rdi+10h], rbx
0x1400bc736  or      qword ptr [rbx+8], 100000h
0x1400bc73e  mov     rcx, rdi; Irp
0x1400bc741  call    cs:__imp_IoSetTopLevelIrp
0x1400bc748  nop     dword ptr [rax+rax+00h]
0x1400bc74d  mov     rax, [rdi+10h]
0x1400bc751  mov     [rbx+68h], rax
0x1400bc755  lea     rdx, [rbx+2A0h]
0x1400bc75c  mov     [rbp+0D0h+var_90], rdx
0x1400bc760  mov     rcx, [rbp+0D0h+var_B0]
0x1400bc764  mov     [rdx], rcx
0x1400bc767  cmp     [rax+158h], r15
0x1400bc76e  jz      loc_1400BC965
0x1400bc774  call    MsRestoreTopLevelContext
0x1400bc779  mov     r9d, 0C0000808h; int
0x1400bc77f  mov     r8, rsi; struct _IRP *
0x1400bc782  mov     rdx, r13; struct REFS_IO_CONTEXT *
0x1400bc785  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1400bc788  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x1400bc78d  mov     eax, 0C0000808h
0x1400bc792  jmp     loc_1400BCE62
0x1400bc797  xor     r12b, r12b
0x1400bc79a  mov     rcx, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; struct _NPAGED_LOOKASIDE_LIST *
0x1400bc7a1  call    ?RefsAllocateNPagedPerProcessorLookaside@@YAPEAXPEAU_NPAGED_LOOKASIDE_LIST@@@Z; RefsAllocateNPagedPerProcessorLookaside(_NPAGED_LOOKASIDE_LIST *)
0x1400bc7a6  mov     rbx, rax
0x1400bc7a9  test    rax, rax
0x1400bc7ac  jnz     loc_1400BC70B
0x1400bc7b2  lea     rax, WPP_GLOBAL_Control
0x1400bc7b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bc7c0  cmp     rcx, rax
0x1400bc7c3  jz      short loc_1400BC7EF
0x1400bc7c5  test    dword ptr [rcx+2Ch], 100h
0x1400bc7cc  jz      short loc_1400BC7EF
0x1400bc7ce  cmp     byte ptr [rcx+29h], 4
0x1400bc7d2  jb      short loc_1400BC7EF
0x1400bc7d4  mov     edx, 0Bh
0x1400bc7d9  mov     r9d, 0C000009Ah
0x1400bc7df  lea     r8, WPP_78e3b6b3f5653fb4a422c7659bfeaffe_Traceguids
0x1400bc7e6  mov     rcx, [rcx+18h]
0x1400bc7ea  call    WPP_SF_d
0x1400bc7ef  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400bc7f6  test    al, al
0x1400bc7f8  jz      loc_1400BC941
0x1400bc7fe  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x1400bc804  lea     rbx, aReadC; "Read.c"
0x1400bc80b  cmp     eax, 0C000009Ah
0x1400bc810  jnz     short loc_1400BC846
0x1400bc812  mov     r9, gs:188h
0x1400bc81b  mov     [rsp+110h+var_E0], 0A7h
0x1400bc823  mov     [rsp+110h+var_E8], rbx
0x1400bc828  mov     [rsp+110h+var_F0], eax
0x1400bc82c  lea     r8, aThPXSI; "th%p %x %s:%i\n"
0x1400bc833  xor     edx, edx; Level
0x1400bc835  mov     ecx, 95h; ComponentId
0x1400bc83a  call    cs:__imp_DbgPrintEx
0x1400bc841  nop     dword ptr [rax+rax+00h]
0x1400bc846  mov     eax, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x1400bc84c  mov     edi, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x1400bc852  cmp     eax, 0C000009Ah
0x1400bc857  jz      short loc_1400BC87A
0x1400bc859  test    edi, edi
0x1400bc85b  jz      loc_1400BC8FD
0x1400bc861  mov     ecx, 0C000009Ah; Status
0x1400bc866  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400bc86d  nop     dword ptr [rax+rax+00h]
0x1400bc872  cmp     edi, eax
0x1400bc874  jnz     loc_1400BC8FD
0x1400bc87a  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x1400bc881  mov     rdi, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x1400bc888  test    rcx, rcx
0x1400bc88b  jz      short loc_1400BC8FB
0x1400bc88d  mov     rax, gs:188h
0x1400bc896  cmp     rcx, rax
0x1400bc899  jnz     short loc_1400BC8FD
0x1400bc89b  test    rdi, rdi
0x1400bc89e  jz      short loc_1400BC8B1
0x1400bc8a0  call    cs:__imp_IoGetCurrentProcess
0x1400bc8a7  nop     dword ptr [rax+rax+00h]
0x1400bc8ac  cmp     rdi, rax
0x1400bc8af  jnz     short loc_1400BC8FD
0x1400bc8b1  cmp     cs:?RefsStatusBreakForImage@@3PADA, r12b; char near * RefsStatusBreakForImage
0x1400bc8b8  jz      short loc_1400BC8F5
0x1400bc8ba  call    cs:__imp_IoGetCurrentProcess
0x1400bc8c1  nop     dword ptr [rax+rax+00h]
0x1400bc8c6  mov     rcx, rax
0x1400bc8c9  call    cs:__imp_PsGetProcessImageFileName
0x1400bc8d0  nop     dword ptr [rax+rax+00h]
0x1400bc8d5  mov     rdx, rax; Str2
0x1400bc8d8  mov     r8d, 0Fh; MaxCount
0x1400bc8de  lea     rcx, ?RefsStatusBreakForImage@@3PADA; Str1
0x1400bc8e5  call    cs:__imp__strnicmp
0x1400bc8ec  nop     dword ptr [rax+rax+00h]
0x1400bc8f1  test    eax, eax
0x1400bc8f3  jnz     short loc_1400BC8FD
0x1400bc8f5  mov     eax, cs:?RefsStatusBreakForFsCtl@@3KC; ulong volatile RefsStatusBreakForFsCtl
0x1400bc8fb  int     2Ch; Windows NT - assertion failure
0x1400bc8fd  mov     ecx, 1
0x1400bc902  lock xadd cs:?RefsStatusNextQueueEntry@@3KA, ecx; ulong RefsStatusNextQueueEntry
0x1400bc90a  inc     ecx
0x1400bc90c  and     ecx, 0FFFh
0x1400bc912  shl     rcx, 5
0x1400bc916  mov     rax, gs:188h
0x1400bc91f  lea     r8, ?RefsStatusQueue@@3PAU_REFS_STATUS_DEBUG_QUEUE_ENTRY@@A; _REFS_STATUS_DEBUG_QUEUE_ENTRY near * RefsStatusQueue
0x1400bc926  mov     [rcx+r8], rax
0x1400bc92a  mov     dword ptr [rcx+r8+8], 0C000009Ah
0x1400bc933  mov     [rcx+r8+10h], rbx
0x1400bc938  mov     dword ptr [rcx+r8+18h], 0A7h
0x1400bc941  mov     rcx, r13
0x1400bc944  call    MsRestoreTopLevelContext
0x1400bc949  mov     r9d, 0C000009Ah; int
0x1400bc94f  mov     r8, rsi; struct _IRP *
0x1400bc952  xor     edx, edx; struct REFS_IO_CONTEXT *
0x1400bc954  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400bc956  call    ?RefsCompleteReadWriteRequest@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteReadWriteRequest(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,long)
0x1400bc95b  mov     eax, 0C000009Ah
0x1400bc960  jmp     loc_1400BCE62
0x1400bc965  mov     [rbp+0D0h+var_B8], rbx
0x1400bc969  mov     [rbp+0D0h+var_78], rdx
0x1400bc96d  mov     edi, r15d
0x1400bc970  mov     r12d, r15d
0x1400bc973  mov     [rbp+0D0h+var_C8], r15d
0x1400bc977  call    cs:__imp_KeEnterCriticalRegion
0x1400bc97e  nop     dword ptr [rax+rax+00h]
0x1400bc983  lea     r8, [rbp+0D0h+var_88]
0x1400bc987  lea     rdx, [rbp+0D0h+var_58]
0x1400bc98b  mov     rcx, rsi
0x1400bc98e  call    cs:__imp_IoPropagateActivityIdToThread
0x1400bc995  nop     dword ptr [rax+rax+00h]
0x1400bc99a  mov     [rbp+0D0h+var_CC], eax
0x1400bc99d  mov     rax, [r14+90h]
0x1400bc9a4  movzx   ecx, byte ptr [rax+2840h]
0x1400bc9ab  test    cl, cl
0x1400bc9ad  jz      short loc_1400BC9C4
0x1400bc9af  xor     ecx, ecx; PerformanceFrequency
0x1400bc9b1  call    cs:__imp_KeQueryPerformanceCounter
0x1400bc9b8  nop     dword ptr [rax+rax+00h]
0x1400bc9bd  mov     [rbx+2B0h], rax
0x1400bc9c4  mov     r14, [rbp+0D0h+var_B0]
0x1400bc9c8  cmp     edi, 0C0000188h
0x1400bc9ce  jnz     short loc_1400BC9DA
0x1400bc9d0  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1400bc9d3  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x1400bc9d8  jmp     short loc_1400BCA0C
0x1400bc9da  mov     ecx, edi
0x1400bc9dc  call    cs:__imp_CcIsCacheManagerCallbackNeeded
0x1400bc9e3  nop     dword ptr [rax+rax+00h]
0x1400bc9e8  test    al, al
0x1400bc9ea  jz      short loc_1400BCA0C
0x1400bc9ec  mov     [rbp+0D0h+var_C0], r15
0x1400bc9f0  mov     eax, 8
0x1400bc9f5  mov     word ptr [rbp+0D0h+var_C0], ax
0x1400bc9f9  mov     dword ptr [rbp+0D0h+var_C0+4], edi
0x1400bc9fc  lea     rcx, [rbp+0D0h+var_C0]
0x1400bca00  call    cs:__imp_CcErrorCallbackRoutine
0x1400bca07  nop     dword ptr [rax+rax+00h]
0x1400bca0c  test    rbx, rbx
0x1400bca0f  jz      loc_1400BCAAA
0x1400bca15  test    r12d, r12d
0x1400bca18  jz      short loc_1400BCA30
0x1400bca1a  mov     r9d, [rsi+10h]
0x1400bca1e  shr     r9d, 1
0x1400bca21  and     r9b, 1; bool
0x1400bca25  mov     rdx, r13; struct REFS_IO_CONTEXT *
0x1400bca28  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1400bca2b  call    ?RefsInitializeIoContext@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@_N2@Z; RefsInitializeIoContext(_IRP_CONTEXT *,REFS_IO_CONTEXT *,bool,bool)
0x1400bca30  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1400bca33  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x1400bca38  mov     rax, [rbp+0D0h+var_90]
0x1400bca3c  mov     [rax], r14
0x1400bca3f  test    byte ptr [rbx+29h], 4
0x1400bca43  jz      short loc_1400BCA52
0x1400bca45  mov     rdx, rsi; Irp
0x1400bca48  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1400bca4b  call    ?RefsCompleteMdl@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsCompleteMdl(_IRP_CONTEXT *,_IRP *)
0x1400bca50  jmp     short loc_1400BCAA5
0x1400bca52  cmp     cs:?RefsFeature_Servicing_ReFSStackSwapRead_IsEnabled@@3EA, 0; uchar RefsFeature_Servicing_ReFSStackSwapRead_IsEnabled
0x1400bca59  jz      short loc_1400BCA97
0x1400bca5b  mov     [rbp+0D0h+HighLimit], r15
0x1400bca5f  mov     [rbp+0D0h+LowLimit], r15
0x1400bca63  lea     rdx, [rbp+0D0h+HighLimit]; HighLimit
0x1400bca67  lea     rcx, [rbp+0D0h+LowLimit]; LowLimit
0x1400bca6b  call    cs:__imp_IoGetStackLimits
0x1400bca72  nop     dword ptr [rax+rax+00h]
0x1400bca77  lea     rax, [rbp+0D0h+HighLimit]
0x1400bca7b  sub     rax, [rbp+0D0h+LowLimit]
0x1400bca7f  mov     r8, rsi; struct _IRP *
0x1400bca82  mov     rdx, r13; struct REFS_IO_CONTEXT *
0x1400bca85  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1400bca88  cmp     rax, 3000h
0x1400bca8e  ja      short loc_1400BCAA0
0x1400bca90  call    ?RefsCommonIoOnNewStack@@YAJPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@@Z; RefsCommonIoOnNewStack(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *)
0x1400bca95  jmp     short loc_1400BCAA5
0x1400bca97  mov     r8, rsi; Irp
0x1400bca9a  mov     rdx, r13; struct REFS_IO_CONTEXT *
0x1400bca9d  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1400bcaa0  call    ?RefsCommonRead@@YAJPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@@Z; RefsCommonRead(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *)
0x1400bcaa5  mov     [rbp+0D0h+var_D0], eax
0x1400bcaa8  mov     edi, eax
0x1400bcaaa  jmp     loc_1400BCB79
0x1400bcaaf  mov     edi, eax
0x1400bcab1  call    Feature_ReFS_Fix_Superseded_Mapped_Views__private_IsEnabledDeviceUsageNoInline
0x1400bcab6  test    eax, eax
0x1400bcab8  jz      loc_1400BCB47
0x1400bcabe  lea     rax, WPP_GLOBAL_Control
0x1400bcac5  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
