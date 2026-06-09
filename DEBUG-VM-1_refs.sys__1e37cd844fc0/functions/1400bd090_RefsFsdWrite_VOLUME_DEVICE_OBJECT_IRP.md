# RefsFsdWrite(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400bd090`
- end: `0x1400bd99c`
- name: `?RefsFsdWrite@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `2316`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000b1b0`
- `0x14000dfe0`
- `0x14000e0e0`
- `0x140038480`
- `0x140050ff0`
- `0x140075660`
- `0x1400892a0`
- `0x14009a130`
- `0x1400a069c`
- `0x1400a2c60`
- `0x1400bd090`
- `0x1400d0fd8`
- `0x1400ef254`
- `0x1400ffac8`
- `0x1400ffb04`
- `0x1401f3fc0`
- `0x14032c7c0`
- `0x14033a7a8`
- `0x14033aca8`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1400bd31a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400bd31a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd2f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd6f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd2f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bd6f2`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400bd710`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1400bd710`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400bd961`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400bd961`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd96d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bd96d`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd19f`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd1b9`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd46f`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd489`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd639`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd653`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd19f`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd1b9`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd46f`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd489`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd639`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400bd653`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400bd291`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1400bd291`
- `ntoskrnl!DbgPrintEx` at `0x1400bd409`
- `ntoskrnl!DbgPrintEx` at `0x1400bd5d3`
- `ntoskrnl!DbgPrintEx` at `0x1400bd409`
- `ntoskrnl!DbgPrintEx` at `0x1400bd5d3`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bd165`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bd435`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bd5ff`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bd165`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bd435`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x1400bd5ff`
- `ntoskrnl!_strnicmp` at `0x1400bd1e4`
- `ntoskrnl!_strnicmp` at `0x1400bd4b4`
- `ntoskrnl!_strnicmp` at `0x1400bd67e`
- `ntoskrnl!_strnicmp` at `0x1400bd1e4`
- `ntoskrnl!_strnicmp` at `0x1400bd4b4`
- `ntoskrnl!_strnicmp` at `0x1400bd67e`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bd1c8`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bd498`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bd662`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bd1c8`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bd498`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1400bd662`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bd835`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bd933`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bd835`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400bd933`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x1400bd85d`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x1400bd85d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bd807`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bd807`
- `HAL!KeQueryPerformanceCounter` at `0x1400bd34f`
- `HAL!KeQueryPerformanceCounter` at `0x1400bd34f`

## string_xrefs

- `0x1400bd3d3`: `write.c`
- `0x1400bd59d`: `write.c`

## pseudocode

```c
__int64 __fastcall RefsFsdWrite(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  int v3; // r12d
  PFILE_OBJECT FileObject; // rcx
  volatile unsigned int v5; // ebx
  struct _KPROCESS *v6; // rbx
  PEPROCESS CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  char v10; // di
  _QWORD *FsContext; // r13
  struct _TOP_LEVEL_CONTEXT *v12; // r15
  void *v13; // rsp
  char *NPagedPerProcessorLookaside; // rdi
  bool v15; // bl
  _BYTE *v16; // r14
  volatile unsigned int v17; // edi
  struct _KPROCESS *v18; // rdi
  PEPROCESS v19; // rax
  const char *v20; // rax
  __int64 v21; // rcx
  volatile unsigned int v22; // edi
  struct _KPROCESS *v23; // rdi
  PEPROCESS v24; // rax
  const char *v25; // rax
  __int64 v26; // rdx
  int Status; // ebx
  bool v28; // r8
  unsigned __int8 v29; // bl
  int v30; // edx
  unsigned int v31; // eax
  char v32; // [rsp+20h] [rbp-680h] BYREF
  char v33; // [rsp+6A0h] [rbp+0h]
  char v34; // [rsp+6A1h] [rbp+1h]
  NTSTATUS v35; // [rsp+6A4h] [rbp+4h]
  int v36; // [rsp+6A8h] [rbp+8h]
  int v37; // [rsp+6ACh] [rbp+Ch]
  __int64 v38; // [rsp+6B0h] [rbp+10h] BYREF
  struct _IRP_CONTEXT *v39; // [rsp+6B8h] [rbp+18h]
  struct REFS_IO_CONTEXT *v40; // [rsp+6C0h] [rbp+20h]
  __int64 v41; // [rsp+6C8h] [rbp+28h] BYREF
  struct _IRP *v42; // [rsp+6D0h] [rbp+30h]
  struct _IRP *v43; // [rsp+6D8h] [rbp+38h]
  struct _TOP_LEVEL_CONTEXT *v44; // [rsp+6E0h] [rbp+40h]
  _QWORD *v45; // [rsp+6E8h] [rbp+48h]
  __int128 v46; // [rsp+6F0h] [rbp+50h] BYREF
  __int64 v47; // [rsp+700h] [rbp+60h]
  __int128 v48; // [rsp+708h] [rbp+68h] BYREF

  v43 = a2;
  v42 = a2;
  v46 = 0;
  v47 = 0;
  v3 = 0;
  v38 = 0;
  v48 = 0;
  v41 = 0;
  FileObject = a2->Tail.Overlay.CurrentStackLocation->FileObject;
  if ( (FileObject->Flags & 0x20000000) != 0 )
  {
    RefsCompleteRequest(0, a2, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_333749fe71273bc3659f43e52285135c_Traceguids, 0);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v5 = RefsStatusBreakOnWin32Error;
      if ( RefsStatusBreakOnWin32Error )
      {
        if ( v5 == RtlNtStatusToDosErrorNoTeb(0) )
        {
          v6 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v6 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (CurrentProcess = IoGetCurrentProcess(),
                 ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess),
                 !_strnicmp(&RefsStatusBreakForImage, ProcessImageFileName, 0xFu))) )
          {
            __int2c();
          }
        }
      }
    }
    return 0;
  }
  v10 = 0;
  v33 = 0;
  v34 = 0;
  FsContext = FileObject->FsContext;
  v45 = FsContext;
  if ( FsContext )
  {
    if ( ((*(_QWORD *)(FsContext[17] + 8LL) & 4) != 0 || (*(_QWORD *)(FsContext[17] + 8LL) & 0x8000LL) != 0)
      && ((*(_QWORD *)(FsContext[17] + 8LL) & 4) != 0 && (FsContext[19] & 0x10) != 0
       || *(_QWORD **)(FsContext[18] + 40LL) == FsContext) )
    {
      v10 = 1;
    }
    v33 = v10;
    v34 = v10;
  }
  v12 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v46, 0, 0);
  v44 = v12;
  if ( v10 )
  {
    if ( (*(_BYTE *)(FsContext[17] + 8LL) & 1) != 0 )
    {
      RefsCompleteRequest(0, a2, -1073741533);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_333749fe71273bc3659f43e52285135c_Traceguids, 3221225763LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        if ( RefsStatusDisplayStatus == -1073741533 )
          DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741533, "write.c", 295);
        v22 = RefsStatusBreakOnWin32Error;
        if ( RefsStatusBreakOnStatus == -1073741533
          || RefsStatusBreakOnWin32Error && v22 == RtlNtStatusToDosErrorNoTeb(-1073741533) )
        {
          v23 = RefsStatusBreakForProcess;
          if ( !RefsStatusBreakForThread
            || RefsStatusBreakForThread == KeGetCurrentThread()
            && (!RefsStatusBreakForProcess || v23 == IoGetCurrentProcess())
            && (!RefsStatusBreakForImage
             || (v24 = IoGetCurrentProcess(),
                 v25 = (const char *)PsGetProcessImageFileName(v24),
                 !_strnicmp(&RefsStatusBreakForImage, v25, 0xFu))) )
          {
            __int2c();
          }
        }
        v26 = 32LL
            * (((unsigned __int16)_InterlockedExchangeAdd((volatile signed __int32 *)&RefsStatusNextQueueEntry, 1u) + 1)
             & 0xFFF);
        *(_QWORD *)((char *)&RefsStatusQueue + v26) = KeGetCurrentThread();
        *(unsigned int *)((char *)&RefsStatusQueue + v26 + 8) = -1073741533;
        *(_QWORD *)((char *)&RefsStatusQueue + v26 + 16) = "write.c";
        *(unsigned int *)((char *)&RefsStatusQueue + v26 + 24) = 295;
      }
      return 3221225763LL;
    }
    NPagedPerProcessorLookaside = 0;
    v39 = 0;
    v16 = 0;
    v40 = 0;
    KeEnterCriticalRegion();
  }
  else
  {
    if ( IoIsOperationSynchronous(a2) && (a2->Flags & 2) != 0 )
    {
      v13 = alloca(1664);
      NPagedPerProcessorLookaside = &v32;
      v15 = 1;
    }
    else
    {
      v15 = 0;
      NPagedPerProcessorLookaside = (char *)RefsAllocateNPagedPerProcessorLookaside(RefsIrpAndIoContextLookasideList);
      if ( !NPagedPerProcessorLookaside )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            &WPP_333749fe71273bc3659f43e52285135c_Traceguids,
            3221225626LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          if ( RefsStatusDisplayStatus == -1073741670 )
            DbgPrintEx(0x95u, 0, "th%p %x %s:%i\n", KeGetCurrentThread(), -1073741670, "write.c", 255);
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
          *(_QWORD *)((char *)&RefsStatusQueue + v21 + 16) = "write.c";
          *(unsigned int *)((char *)&RefsStatusQueue + v21 + 24) = 255;
        }
        RefsCompleteRequest(0, a2, -1073741670);
        return 3221225626LL;
      }
    }
    RefsInitializeIrpAndIoContext(a2, (struct IRP_AND_IO_CONTEXT *)NPagedPerProcessorLookaside, v15);
    v39 = (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside;
    v16 = NPagedPerProcessorLookaside + 800;
    v40 = (struct REFS_IO_CONTEXT *)(NPagedPerProcessorLookaside + 800);
    if ( (NPagedPerProcessorLookaside[41] & 6) == 2 )
      a2->MdlAddress = 0;
    KeEnterCriticalRegion();
    if ( !*((_QWORD *)v12 + 2) )
    {
      *((_DWORD *)v12 + 1) = 1397140410;
      *((_QWORD *)v12 + 2) = NPagedPerProcessorLookaside;
      *((_QWORD *)NPagedPerProcessorLookaside + 1) |= 0x100000uLL;
      IoSetTopLevelIrp((PIRP)v12);
    }
    *((_QWORD *)NPagedPerProcessorLookaside + 13) = *((_QWORD *)v12 + 2);
    if ( FsContext && *(_BYTE *)(FsContext[18] + 10304LL) )
      *((LARGE_INTEGER *)NPagedPerProcessorLookaside + 86) = KeQueryPerformanceCounter(0);
  }
  Status = 0;
  v37 = 0;
  v36 = IoPropagateActivityIdToThread(a2, &v48, &v41);
  while ( !v33 )
  {
    if ( v3 )
      RefsInitializeIoContext(
        (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside,
        (struct REFS_IO_CONTEXT *)v16,
        v28,
        (a2->Flags & 2) != 0);
    if ( Status == -1073741432 )
    {
      RefsCheckpointForLogFileFull((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside);
    }
    else if ( Status == 871 )
    {
      v42->Tail.Overlay.CurrentStackLocation->Control &= ~1u;
      v35 = KeWaitForSingleObject(v16 + 8, Executive, 0, 0, 0);
      Status = a2->IoStatus.Status;
      v35 = Status;
      if ( Status < 0 )
      {
        RefsCompleteRequest((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, a2, Status);
        goto LABEL_113;
      }
    }
    else if ( (unsigned __int8)CcIsCacheManagerCallbackNeeded((unsigned int)Status) )
    {
      LODWORD(v38) = 8;
      HIDWORD(v38) = Status;
      CcErrorCallbackRoutine(&v38);
    }
    if ( NPagedPerProcessorLookaside )
      RefsPreRequestProcessingExtend((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, v30);
    if ( (NPagedPerProcessorLookaside[41] & 4) != 0 )
    {
      v31 = RefsCompleteMdl((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, a2);
    }
    else if ( (a2->Flags & 2) != 0 )
    {
      v31 = RefsCommonIoOnNewStack(
              (struct _IRP_CONTEXT *)NPagedPerProcessorLookaside,
              (struct REFS_IO_CONTEXT *)v16,
              a2);
    }
    else
    {
      v31 = RefsCommonWrite((struct _IRP_CONTEXT *)NPagedPerProcessorLookaside, (struct REFS_IO_CONTEXT *)v16, a2);
    }
    Status = v31;
    v35 = v31;
    if ( v31
      && (v31 == -1073741608
       || v31 == -1073741432
       || v31 == -1073741400
       || v31 == 871
       || (unsigned __int8)CcIsCacheManagerCallbackNeeded(v31)) )
    {
      v37 = ++v3;
      if ( v12 == (struct _TOP_LEVEL_CONTEXT *)&v46 )
        continue;
    }
    goto LABEL_113;
  }
  if ( v12 == (struct _TOP_LEVEL_CONTEXT *)&v46 )
    v29 = 0;
  else
    v29 = RefsSetTopLevelWithoutIrpContext(v12);
  RefsPagingFileIo(a2, (struct _SCB *)FsContext);
  if ( v29 )
    RefsRestoreTopLevelIrpWithoutContext();
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
  {
    Status = 259;
  }
  else
  {
    Status = 259;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_333749fe71273bc3659f43e52285135c_Traceguids, 259);
  }
  v35 = 259;
LABEL_113:
  if ( v36 >= 0 )
    IoClearActivityIdThread(v41);
  KeLeaveCriticalRegion();
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400bd090  push    rbp
0x1400bd092  push    rbx
0x1400bd093  push    rsi
0x1400bd094  push    rdi
0x1400bd095  push    r12
0x1400bd097  push    r13
0x1400bd099  push    r14
0x1400bd09b  push    r15
0x1400bd09d  sub     rsp, 0C8h
0x1400bd0a4  lea     rbp, [rsp+40h]
0x1400bd0a9  mov     rax, cs:__security_cookie
0x1400bd0b0  xor     rax, rbp
0x1400bd0b3  mov     [rbp+0C0h+var_48], rax
0x1400bd0b7  mov     rsi, rdx
0x1400bd0ba  mov     [rbp+0C0h+var_88], rdx
0x1400bd0be  mov     [rbp+0C0h+var_90], rdx
0x1400bd0c2  xorps   xmm0, xmm0
0x1400bd0c5  xor     ecx, ecx
0x1400bd0c7  movups  [rbp+0C0h+var_70], xmm0
0x1400bd0cb  mov     [rbp+0C0h+var_60], rcx
0x1400bd0cf  xor     r12d, r12d
0x1400bd0d2  mov     [rbp+0C0h+var_B0], r12
0x1400bd0d6  movups  [rbp+0C0h+var_58], xmm0
0x1400bd0da  mov     [rbp+0C0h+var_98], r12
0x1400bd0de  mov     rax, [rdx+0B8h]
0x1400bd0e5  mov     rcx, [rax+30h]
0x1400bd0e9  mov     eax, [rcx+50h]
0x1400bd0ec  bt      eax, 1Dh
0x1400bd0f0  jnb     loc_1400BD203
0x1400bd0f6  xor     r8d, r8d; Status
0x1400bd0f9  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400bd0fb  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1400bd100  lea     rax, WPP_GLOBAL_Control
0x1400bd107  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd10e  cmp     rcx, rax
0x1400bd111  jz      short loc_1400BD13A
0x1400bd113  test    dword ptr [rcx+2Ch], 100h
0x1400bd11a  jz      short loc_1400BD13A
0x1400bd11c  cmp     byte ptr [rcx+29h], 5
0x1400bd120  jb      short loc_1400BD13A
0x1400bd122  mov     edx, 0Ah
0x1400bd127  xor     r9d, r9d
0x1400bd12a  lea     r8, WPP_333749fe71273bc3659f43e52285135c_Traceguids
0x1400bd131  mov     rcx, [rcx+18h]
0x1400bd135  call    WPP_SF_d
0x1400bd13a  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400bd141  test    al, al
0x1400bd143  jz      loc_1400BD1FC
0x1400bd149  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x1400bd14f  mov     eax, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x1400bd155  mov     ebx, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x1400bd15b  test    ebx, ebx
0x1400bd15d  jz      loc_1400BD1FC
0x1400bd163  xor     ecx, ecx; Status
0x1400bd165  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400bd16c  nop     dword ptr [rax+rax+00h]
0x1400bd171  cmp     ebx, eax
0x1400bd173  jnz     loc_1400BD1FC
0x1400bd179  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x1400bd180  mov     rbx, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x1400bd187  test    rcx, rcx
0x1400bd18a  jz      short loc_1400BD1FA
0x1400bd18c  mov     rax, gs:188h
0x1400bd195  cmp     rcx, rax
0x1400bd198  jnz     short loc_1400BD1FC
0x1400bd19a  test    rbx, rbx
0x1400bd19d  jz      short loc_1400BD1B0
0x1400bd19f  call    cs:__imp_IoGetCurrentProcess
0x1400bd1a6  nop     dword ptr [rax+rax+00h]
0x1400bd1ab  cmp     rbx, rax
0x1400bd1ae  jnz     short loc_1400BD1FC
0x1400bd1b0  cmp     cs:?RefsStatusBreakForImage@@3PADA, r12b; char near * RefsStatusBreakForImage
0x1400bd1b7  jz      short loc_1400BD1F4
0x1400bd1b9  call    cs:__imp_IoGetCurrentProcess
0x1400bd1c0  nop     dword ptr [rax+rax+00h]
0x1400bd1c5  mov     rcx, rax
0x1400bd1c8  call    cs:__imp_PsGetProcessImageFileName
0x1400bd1cf  nop     dword ptr [rax+rax+00h]
0x1400bd1d4  mov     rdx, rax; Str2
0x1400bd1d7  mov     r8d, 0Fh; MaxCount
0x1400bd1dd  lea     rcx, ?RefsStatusBreakForImage@@3PADA; Str1
0x1400bd1e4  call    cs:__imp__strnicmp
0x1400bd1eb  nop     dword ptr [rax+rax+00h]
0x1400bd1f0  test    eax, eax
0x1400bd1f2  jnz     short loc_1400BD1FC
0x1400bd1f4  mov     eax, cs:?RefsStatusBreakForFsCtl@@3KC; ulong volatile RefsStatusBreakForFsCtl
0x1400bd1fa  int     2Ch; Windows NT - assertion failure
0x1400bd1fc  xor     eax, eax
0x1400bd1fe  jmp     loc_1400BD97B
0x1400bd203  xor     dil, dil
0x1400bd206  mov     [rbp+0C0h+var_C0], dil
0x1400bd20a  mov     [rbp+0C0h+var_BF], dil
0x1400bd20e  mov     r13, [rcx+18h]
0x1400bd212  mov     [rbp+0C0h+var_78], r13
0x1400bd216  test    r13, r13
0x1400bd219  jz      short loc_1400BD270
0x1400bd21b  mov     rax, [r13+88h]
0x1400bd222  mov     rcx, [rax+8]
0x1400bd226  test    cl, 4
0x1400bd229  jnz     short loc_1400BD23D
0x1400bd22b  mov     rax, [r13+88h]
0x1400bd232  mov     rcx, [rax+8]
0x1400bd236  bt      rcx, 0Fh
0x1400bd23b  jnb     short loc_1400BD268
0x1400bd23d  mov     rax, [r13+88h]
0x1400bd244  mov     rcx, [rax+8]
0x1400bd248  test    cl, 4
0x1400bd24b  jz      short loc_1400BD258
0x1400bd24d  mov     eax, [r13+98h]
0x1400bd254  test    al, 10h
0x1400bd256  jnz     short loc_1400BD265
0x1400bd258  mov     rax, [r13+90h]
0x1400bd25f  cmp     [rax+28h], r13
0x1400bd263  jnz     short loc_1400BD268
0x1400bd265  mov     dil, 1
0x1400bd268  mov     [rbp+0C0h+var_C0], dil
0x1400bd26c  mov     [rbp+0C0h+var_BF], dil
0x1400bd270  xor     r8d, r8d; unsigned __int8
0x1400bd273  xor     edx, edx; unsigned __int8
0x1400bd275  lea     rcx, [rbp+0C0h+var_70]; struct _TOP_LEVEL_CONTEXT *
0x1400bd279  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x1400bd27e  mov     r15, rax
0x1400bd281  mov     [rbp+0C0h+var_80], rax
0x1400bd285  test    dil, dil
0x1400bd288  jnz     loc_1400BD52A
0x1400bd28e  mov     rcx, rsi; Irp
0x1400bd291  call    cs:__imp_IoIsOperationSynchronous
0x1400bd298  nop     dword ptr [rax+rax+00h]
0x1400bd29d  test    al, al
0x1400bd29f  jz      loc_1400BD367
0x1400bd2a5  mov     ecx, [rsi+10h]
0x1400bd2a8  test    cl, 2
0x1400bd2ab  jz      loc_1400BD367
0x1400bd2b1  mov     eax, [rsp+100h+var_100]
0x1400bd2b4  mov     eax, 680h
0x1400bd2b9  sub     rsp, rax
0x1400bd2bc  lea     rdi, [rsp+780h+var_740]
0x1400bd2c1  mov     eax, [rdi]
0x1400bd2c3  mov     bl, 1
0x1400bd2c5  movzx   r8d, bl; bool
0x1400bd2c9  mov     rdx, rdi; struct IRP_AND_IO_CONTEXT *
0x1400bd2cc  mov     rcx, rsi; Irp
0x1400bd2cf  call    ?RefsInitializeIrpAndIoContext@@YAXPEAU_IRP@@PEAUIRP_AND_IO_CONTEXT@@_N@Z; RefsInitializeIrpAndIoContext(_IRP *,IRP_AND_IO_CONTEXT *,bool)
0x1400bd2d4  mov     [rbp+0C0h+var_A8], rdi
0x1400bd2d8  lea     r14, [rdi+320h]
0x1400bd2df  mov     [rbp+0C0h+var_A0], r14
0x1400bd2e3  movzx   eax, byte ptr [rdi+29h]
0x1400bd2e7  and     al, 6
0x1400bd2e9  cmp     al, 2
0x1400bd2eb  jnz     short loc_1400BD2F1
0x1400bd2ed  mov     [rsi+8], r12
0x1400bd2f1  call    cs:__imp_KeEnterCriticalRegion
0x1400bd2f8  nop     dword ptr [rax+rax+00h]
0x1400bd2fd  cmp     [r15+10h], r12
0x1400bd301  jnz     short loc_1400BD326
0x1400bd303  mov     dword ptr [r15+4], 5346ABBAh
0x1400bd30b  mov     [r15+10h], rdi
0x1400bd30f  or      qword ptr [rdi+8], 100000h
0x1400bd317  mov     rcx, r15; Irp
0x1400bd31a  call    cs:__imp_IoSetTopLevelIrp
0x1400bd321  nop     dword ptr [rax+rax+00h]
0x1400bd326  mov     rax, [r15+10h]
0x1400bd32a  mov     [rdi+68h], rax
0x1400bd32e  test    r13, r13
0x1400bd331  jz      loc_1400BD6FE
0x1400bd337  mov     rax, [r13+90h]
0x1400bd33e  movzx   ecx, byte ptr [rax+2840h]
0x1400bd345  test    cl, cl
0x1400bd347  jz      loc_1400BD6FE
0x1400bd34d  xor     ecx, ecx; PerformanceFrequency
0x1400bd34f  call    cs:__imp_KeQueryPerformanceCounter
0x1400bd356  nop     dword ptr [rax+rax+00h]
0x1400bd35b  mov     [rdi+2B0h], rax
0x1400bd362  jmp     loc_1400BD6FE
0x1400bd367  xor     bl, bl
0x1400bd369  mov     rcx, cs:?RefsIrpAndIoContextLookasideList@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; struct _NPAGED_LOOKASIDE_LIST *
0x1400bd370  call    ?RefsAllocateNPagedPerProcessorLookaside@@YAPEAXPEAU_NPAGED_LOOKASIDE_LIST@@@Z; RefsAllocateNPagedPerProcessorLookaside(_NPAGED_LOOKASIDE_LIST *)
0x1400bd375  mov     rdi, rax
0x1400bd378  test    rax, rax
0x1400bd37b  jnz     loc_1400BD2C5
0x1400bd381  lea     rax, WPP_GLOBAL_Control
0x1400bd388  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd38f  cmp     rcx, rax
0x1400bd392  jz      short loc_1400BD3BE
0x1400bd394  test    dword ptr [rcx+2Ch], 100h
0x1400bd39b  jz      short loc_1400BD3BE
0x1400bd39d  cmp     byte ptr [rcx+29h], 4
0x1400bd3a1  jb      short loc_1400BD3BE
0x1400bd3a3  mov     edx, 0Bh
0x1400bd3a8  mov     r9d, 0C000009Ah
0x1400bd3ae  lea     r8, WPP_333749fe71273bc3659f43e52285135c_Traceguids
0x1400bd3b5  mov     rcx, [rcx+18h]
0x1400bd3b9  call    WPP_SF_d
0x1400bd3be  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400bd3c5  test    al, al
0x1400bd3c7  jz      loc_1400BD510
0x1400bd3cd  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x1400bd3d3  lea     rbx, aWriteC; "write.c"
0x1400bd3da  cmp     eax, 0C000009Ah
0x1400bd3df  jnz     short loc_1400BD415
0x1400bd3e1  mov     r9, gs:188h
0x1400bd3ea  mov     [rsp+100h+var_D0], 0FFh
0x1400bd3f2  mov     [rsp+100h+var_D8], rbx
0x1400bd3f7  mov     dword ptr [rsp+100h+var_E0], eax
0x1400bd3fb  lea     r8, aThPXSI; "th%p %x %s:%i\n"
0x1400bd402  xor     edx, edx; Level
0x1400bd404  mov     ecx, 95h; ComponentId
0x1400bd409  call    cs:__imp_DbgPrintEx
0x1400bd410  nop     dword ptr [rax+rax+00h]
0x1400bd415  mov     eax, cs:?RefsStatusBreakOnStatus@@3JC; long volatile RefsStatusBreakOnStatus
0x1400bd41b  mov     edi, cs:?RefsStatusBreakOnWin32Error@@3KC; ulong volatile RefsStatusBreakOnWin32Error
0x1400bd421  cmp     eax, 0C000009Ah
0x1400bd426  jz      short loc_1400BD449
0x1400bd428  test    edi, edi
0x1400bd42a  jz      loc_1400BD4CC
0x1400bd430  mov     ecx, 0C000009Ah; Status
0x1400bd435  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1400bd43c  nop     dword ptr [rax+rax+00h]
0x1400bd441  cmp     edi, eax
0x1400bd443  jnz     loc_1400BD4CC
0x1400bd449  mov     rcx, cs:?RefsStatusBreakForThread@@3REAU_KTHREAD@@EA; _KTHREAD * RefsStatusBreakForThread
0x1400bd450  mov     rdi, cs:?RefsStatusBreakForProcess@@3REAU_KPROCESS@@EA; _KPROCESS * RefsStatusBreakForProcess
0x1400bd457  test    rcx, rcx
0x1400bd45a  jz      short loc_1400BD4CA
0x1400bd45c  mov     rax, gs:188h
0x1400bd465  cmp     rcx, rax
0x1400bd468  jnz     short loc_1400BD4CC
0x1400bd46a  test    rdi, rdi
0x1400bd46d  jz      short loc_1400BD480
0x1400bd46f  call    cs:__imp_IoGetCurrentProcess
0x1400bd476  nop     dword ptr [rax+rax+00h]
0x1400bd47b  cmp     rdi, rax
0x1400bd47e  jnz     short loc_1400BD4CC
0x1400bd480  cmp     cs:?RefsStatusBreakForImage@@3PADA, r12b; char near * RefsStatusBreakForImage
0x1400bd487  jz      short loc_1400BD4C4
0x1400bd489  call    cs:__imp_IoGetCurrentProcess
0x1400bd490  nop     dword ptr [rax+rax+00h]
0x1400bd495  mov     rcx, rax
0x1400bd498  call    cs:__imp_PsGetProcessImageFileName
0x1400bd49f  nop     dword ptr [rax+rax+00h]
0x1400bd4a4  mov     rdx, rax; Str2
0x1400bd4a7  mov     r8d, 0Fh; MaxCount
0x1400bd4ad  lea     rcx, ?RefsStatusBreakForImage@@3PADA; Str1
0x1400bd4b4  call    cs:__imp__strnicmp
0x1400bd4bb  nop     dword ptr [rax+rax+00h]
0x1400bd4c0  test    eax, eax
0x1400bd4c2  jnz     short loc_1400BD4CC
0x1400bd4c4  mov     eax, cs:?RefsStatusBreakForFsCtl@@3KC; ulong volatile RefsStatusBreakForFsCtl
0x1400bd4ca  int     2Ch; Windows NT - assertion failure
0x1400bd4cc  mov     ecx, 1
0x1400bd4d1  lock xadd cs:?RefsStatusNextQueueEntry@@3KA, ecx; ulong RefsStatusNextQueueEntry
0x1400bd4d9  inc     ecx
0x1400bd4db  and     ecx, 0FFFh
0x1400bd4e1  shl     rcx, 5
0x1400bd4e5  mov     rax, gs:188h
0x1400bd4ee  lea     r8, ?RefsStatusQueue@@3PAU_REFS_STATUS_DEBUG_QUEUE_ENTRY@@A; _REFS_STATUS_DEBUG_QUEUE_ENTRY near * RefsStatusQueue
0x1400bd4f5  mov     [rcx+r8], rax
0x1400bd4f9  mov     dword ptr [rcx+r8+8], 0C000009Ah
0x1400bd502  mov     [rcx+r8+10h], rbx
0x1400bd507  mov     dword ptr [rcx+r8+18h], 0FFh
0x1400bd510  mov     r8d, 0C000009Ah; Status
0x1400bd516  mov     rdx, rsi; Irp
0x1400bd519  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400bd51b  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1400bd520  mov     eax, 0C000009Ah
0x1400bd525  jmp     loc_1400BD97B
0x1400bd52a  mov     rax, [r13+88h]
0x1400bd531  test    byte ptr [rax+8], 1
0x1400bd535  jz      loc_1400BD6E4
0x1400bd53b  mov     r8d, 0C0000123h; Status
0x1400bd541  mov     rdx, rsi; Irp
0x1400bd544  xor     ecx, ecx; struct _IRP_CONTEXT *
0x1400bd546  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1400bd54b  lea     rax, WPP_GLOBAL_Control
0x1400bd552  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bd559  cmp     rcx, rax
0x1400bd55c  jz      short loc_1400BD588
0x1400bd55e  test    dword ptr [rcx+2Ch], 100h
0x1400bd565  jz      short loc_1400BD588
0x1400bd567  cmp     byte ptr [rcx+29h], 4
0x1400bd56b  jb      short loc_1400BD588
0x1400bd56d  mov     edx, 0Ch
0x1400bd572  mov     r9d, 0C0000123h
0x1400bd578  lea     r8, WPP_333749fe71273bc3659f43e52285135c_Traceguids
0x1400bd57f  mov     rcx, [rcx+18h]
0x1400bd583  call    WPP_SF_d
0x1400bd588  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400bd58f  test    al, al
0x1400bd591  jz      loc_1400BD6DA
0x1400bd597  mov     eax, cs:?RefsStatusDisplayStatus@@3JC; long volatile RefsStatusDisplayStatus
0x1400bd59d  lea     rbx, aWriteC; "write.c"
0x1400bd5a4  cmp     eax, 0C0000123h
0x1400bd5a9  jnz     short loc_1400BD5DF
0x1400bd5ab  mov     r9, gs:188h
0x1400bd5b4  mov     [rsp+100h+var_D0], 127h
0x1400bd5bc  mov     [rsp+100h+var_D8], rbx
0x1400bd5c1  mov     dword ptr [rsp+100h+var_E0], eax
0x1400bd5c5  lea     r8, aThPXSI; "th%p %x %s:%i\n"
0x1400bd5cc  xor     edx, edx; Level
0x1400bd5ce  mov     ecx, 95h; ComponentId
  ... truncated ...
```
