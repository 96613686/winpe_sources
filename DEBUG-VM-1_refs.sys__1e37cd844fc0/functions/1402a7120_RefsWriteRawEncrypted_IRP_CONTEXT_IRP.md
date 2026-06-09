# RefsWriteRawEncrypted(_IRP_CONTEXT *,_IRP *)

- ea: `0x1402a7120`
- end: `0x1402a8a41`
- name: `?RefsWriteRawEncrypted@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `6433`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x140323dd8`

## callees

- `0x14000e0e0`
- `0x140037e00`
- `0x140072a40`
- `0x140075ff0`
- `0x140076ad0`
- `0x14007cdb0`
- `0x1400862c0`
- `0x140095370`
- `0x1400cf1bc`
- `0x1400d0fd8`
- `0x1400e7a10`
- `0x1400e7c94`
- `0x1400f5020`
- `0x1400fe714`
- `0x140111604`
- `0x1401f4100`
- `0x1401f4400`
- `0x140294e98`
- `0x1402a7120`
- `0x1402a8a48`
- `0x140302e10`
- `0x140323140`
- `0x14032cb40`
- `0x140332094`
- `0x14033819c`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x1402a7da1`
- `ntoskrnl!IoFreeIrp` at `0x1402a7e65`
- `ntoskrnl!IoFreeIrp` at `0x1402a7da1`
- `ntoskrnl!IoFreeIrp` at `0x1402a7e65`
- `ntoskrnl!IoAllocateMdl` at `0x1402a7d89`
- `ntoskrnl!IoAllocateMdl` at `0x1402a7d89`
- `ntoskrnl!MmProbeAndLockPages` at `0x1402a7e13`
- `ntoskrnl!MmProbeAndLockPages` at `0x1402a7e13`
- `ntoskrnl!IoFreeMdl` at `0x1402a7e4e`
- `ntoskrnl!IoFreeMdl` at `0x1402a7e4e`
- `ntoskrnl!MmMdlPageContentsState` at `0x1402a7e27`
- `ntoskrnl!MmMdlPageContentsState` at `0x1402a7e27`
- `ntoskrnl!IofCallDriver` at `0x1402a7f5b`
- `ntoskrnl!IofCallDriver` at `0x1402a7f5b`
- `ntoskrnl!ProbeForRead` at `0x1402a756f`
- `ntoskrnl!ProbeForRead` at `0x1402a756f`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1402a7cdb`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1402a7cdb`
- `ntoskrnl!CcFlushCache` at `0x1402a7834`
- `ntoskrnl!CcFlushCache` at `0x1402a7834`
- `ntoskrnl!CcPurgeCacheSection` at `0x1402a785f`
- `ntoskrnl!CcPurgeCacheSection` at `0x1402a785f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a7f8b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a7f8b`
- `ntoskrnl!KeInitializeEvent` at `0x1402a7218`
- `ntoskrnl!KeInitializeEvent` at `0x1402a7218`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7b99`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a86c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140347294`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a7b99`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a86c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140347294`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a7bec`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402a7bec`
- `ntoskrnl!CcSetFileSizesEx` at `0x1402a84a5`
- `ntoskrnl!CcSetFileSizesEx` at `0x1402a85d0`
- `ntoskrnl!CcSetFileSizesEx` at `0x1402a84a5`
- `ntoskrnl!CcSetFileSizesEx` at `0x1402a85d0`

## pseudocode

```c
__int64 __fastcall RefsWriteRawEncrypted(struct _IRP_CONTEXT *a1, PIRP Irp)
{
  char v4; // r12
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int v6; // r15d
  unsigned int v7; // r9d
  __int64 v9; // r13
  unsigned __int64 v10; // rdx
  __int16 v11; // r8
  SIZE_T Options; // rcx
  union _LARGE_INTEGER *Parameters; // r13
  struct _SCB *v14; // rsi
  unsigned __int64 LowPart; // r11
  DWORD v16; // r10d
  int LowPart_high; // r8d
  char v18; // dl
  __int16 v19; // r9
  __int64 v20; // rax
  __int16 v21; // r9
  unsigned __int8 v22; // r8
  int v23; // r9d
  int v24; // edx
  unsigned __int16 v25; // r8
  unsigned __int16 v26; // r12
  int v27; // ecx
  __int64 v28; // rbx
  signed __int64 v29; // rax
  unsigned __int16 v30; // r8
  struct _SCB *v31; // rdx
  __int64 v32; // r10
  char v33; // cl
  unsigned int v34; // r12d
  unsigned int v35; // ecx
  ULONG v36; // r13d
  unsigned __int64 v37; // rbx
  unsigned __int64 v38; // r8
  unsigned int v39; // r9d
  unsigned __int64 PoolWithTag; // r9
  PIRP v41; // rax
  IRP *v42; // rbx
  unsigned int v43; // r9d
  struct _MDL *Mdl; // rax
  struct _IO_STACK_LOCATION *v45; // rdx
  __int64 v46; // r13
  unsigned __int8 v47; // r8
  int v48; // r9d
  unsigned int v49; // r9d
  unsigned int v50; // ebx
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r9
  DWORD v54; // edx
  __int64 v55; // r10
  __int64 v56; // rax
  char v57; // cl
  __int64 v58; // r11
  __int64 v59; // r8
  __int64 v60; // rax
  __int64 v61; // r12
  __int64 v62; // r13
  __int64 v63; // r13
  __int64 v64; // r12
  LONGLONG v65; // rbx
  __int64 v66; // r15
  union _LARGE_INTEGER v67; // r12
  LONGLONG v68; // rbx
  LONGLONG v69; // rax
  struct _FILE_OBJECT *v70; // rcx
  int v71; // eax
  bool v72; // cf
  __int64 v73; // [rsp+0h] [rbp-1C8h] BYREF
  PLARGE_INTEGER StartingOffset; // [rsp+20h] [rbp-1A8h]
  PKEVENT v75; // [rsp+28h] [rbp-1A0h]
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-198h]
  char v77; // [rsp+60h] [rbp-168h]
  NTSTATUS Status; // [rsp+64h] [rbp-164h] BYREF
  unsigned __int16 v79; // [rsp+68h] [rbp-160h]
  char v80; // [rsp+6Ah] [rbp-15Eh]
  char v81; // [rsp+6Bh] [rbp-15Dh]
  union _LARGE_INTEGER v82; // [rsp+70h] [rbp-158h] BYREF
  int v83; // [rsp+78h] [rbp-150h]
  __int64 v84; // [rsp+80h] [rbp-148h] BYREF
  unsigned int v85; // [rsp+88h] [rbp-140h]
  struct _SCB *v86; // [rsp+90h] [rbp-138h] BYREF
  PVOID VirtualAddress; // [rsp+98h] [rbp-130h]
  char v88; // [rsp+A0h] [rbp-128h]
  __int16 v89; // [rsp+A4h] [rbp-124h]
  int v90; // [rsp+A8h] [rbp-120h]
  DWORD v91; // [rsp+ACh] [rbp-11Ch]
  unsigned int HighPart; // [rsp+B0h] [rbp-118h]
  void *v93; // [rsp+B8h] [rbp-110h]
  __int64 v94; // [rsp+C0h] [rbp-108h] BYREF
  unsigned int v95; // [rsp+C8h] [rbp-100h]
  ULONG v96; // [rsp+CCh] [rbp-FCh]
  struct _FCB *v97; // [rsp+D0h] [rbp-F8h] BYREF
  PVOID P; // [rsp+D8h] [rbp-F0h]
  __int16 v99; // [rsp+E0h] [rbp-E8h]
  DWORD v100; // [rsp+E8h] [rbp-E0h]
  unsigned int v101; // [rsp+ECh] [rbp-DCh]
  PIRP Irpa; // [rsp+F0h] [rbp-D8h]
  unsigned __int64 v103; // [rsp+F8h] [rbp-D0h]
  __int64 v104; // [rsp+100h] [rbp-C8h]
  union _LARGE_INTEGER *v105; // [rsp+108h] [rbp-C0h]
  union _LARGE_INTEGER v106; // [rsp+110h] [rbp-B8h]
  ULONG v107; // [rsp+118h] [rbp-B0h]
  union _LARGE_INTEGER v108; // [rsp+120h] [rbp-A8h]
  PFILE_OBJECT FileObject; // [rsp+128h] [rbp-A0h]
  __int64 v110; // [rsp+130h] [rbp-98h]
  struct _SCB *v111; // [rsp+138h] [rbp-90h]
  struct _KEVENT Event; // [rsp+140h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK v113; // [rsp+158h] [rbp-70h] BYREF
  __int128 v114; // [rsp+170h] [rbp-58h]
  __int128 v115[4]; // [rsp+180h] [rbp-48h] BYREF
  __int64 v117; // [rsp+1E0h] [rbp+18h]
  char v118; // [rsp+1E0h] [rbp+18h]
  unsigned __int64 v119; // [rsp+1E8h] [rbp+20h] BYREF

  v82.QuadPart = 0;
  v108.QuadPart = 0;
  v100 = 0;
  v101 = 0;
  v84 = 0;
  v97 = 0;
  v86 = 0;
  v119 = 0;
  v90 = 0;
  v89 = 0;
  v77 = 0;
  v80 = 0;
  memset(&Event, 0, sizeof(Event));
  v113 = 0;
  v4 = 0;
  v81 = 0;
  Status = 0;
  v117 = (unsigned int)Feature_ReFS_EFS__private_featureState;
  if ( (Feature_ReFS_EFS__private_featureState & 0x10) == 0 )
  {
    LODWORD(v117) = Feature_ReFS_EFS__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(&Feature_ReFS_EFS__private_descriptor, v117, 3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v117, 3, &Feature_ReFS_EFS__private_descriptor);
  }
  *((_QWORD *)a1 + 1) |= 1uLL;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  LOBYTE(IoStatusBlock) = 1;
  v75 = (PKEVENT)&v119;
  StartingOffset = (PLARGE_INTEGER)&v86;
  if ( (unsigned __int8)RefsDecodeFileObject(a1, FileObject, &v84, &v97) != 2 )
  {
    v6 = -1073741811;
    RefsCompleteRequest(a1, Irp, -1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 69, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v6;
    v7 = 3749;
LABEL_10:
    RefsStatusDebug(v6, 0, "Efssup.c", v7);
    return v6;
  }
  v9 = v84;
  if ( (*(_DWORD *)(v84 + 24) & 0x2000000) != 0 )
  {
    v6 = -1073741662;
    RefsCompleteRequest(a1, Irp, -1073741662);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225634LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v6;
    v7 = 3759;
    goto LABEL_10;
  }
  v10 = v119;
  *((_DWORD *)a1 + 158) = *(_DWORD *)(v119 + 84);
  v11 = *(_WORD *)(v10 + 88);
  if ( (v11 & 0x12) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqZqiiiZD(
        WPP_GLOBAL_Control->AttachedDevice,
        71,
        v9 + 6152,
        (unsigned int)KeGetCurrentThread(),
        v9,
        v9 + 6152,
        (char)v97,
        (char)v97->pNetRoot[2].Context,
        (char)v97->pNetRoot[2].pSrvCall,
        (char)v97->InternalFobx,
        v10 + 16,
        v11);
    }
    v6 = -1073741790;
    RefsCompleteRequest(a1, Irp, -1073741790);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 72, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225506LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v6;
    v7 = 3789;
    goto LABEL_10;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  v85 = Options;
  if ( (unsigned int)Options < 0x20 )
  {
    v6 = -1073741789;
    RefsCompleteRequest(a1, Irp, -1073741789);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 73, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225507LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v6;
    v7 = 3806;
    goto LABEL_10;
  }
  Parameters = (union _LARGE_INTEGER *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
  v105 = Parameters;
  v14 = v86;
  if ( CurrentStackLocation[-1].Parameters.Read.Length == -1 )
  {
    LODWORD(v94) = 0;
    LODWORD(VirtualAddress) = 0;
    LOBYTE(v119) = 0;
    CurrentStackLocation[-1].Parameters.Read.Length = 0;
    CurrentStackLocation[-1].Parameters.Create.Options = *((_DWORD *)v14 + 10);
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = *((_DWORD *)v14 + 11);
  }
  else
  {
    LOBYTE(v119) = 1;
    LODWORD(v94) = CurrentStackLocation[-1].Parameters.Create.Options;
    LODWORD(VirtualAddress) = CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart;
  }
  v77 = 1;
  if ( Irp->RequestorMode )
  {
    ProbeForRead(Parameters, Options, 1u);
    LODWORD(Options) = v85;
  }
  LowPart = Parameters[1].LowPart;
  v95 = LowPart;
  v90 = LowPart;
  v16 = Parameters[2].LowPart;
  v91 = v16;
  v100 = v16;
  HighPart = Parameters[1].HighPart;
  v101 = HighPart;
  LowPart_high = HIWORD(Parameters[3].u.LowPart);
  v79 = LowPart_high;
  v89 = LowPart_high;
  v18 = BYTE1(Parameters[3].LowPart);
  v88 = v18;
  v106 = *Parameters;
  v82 = v106;
  v108 = v106;
  v118 = BYTE6(Parameters[2].QuadPart);
  v80 = v118;
  v19 = WORD2(Parameters[2].QuadPart);
  v99 = v19;
  v20 = (unsigned int)(4 * LowPart_high + 28);
  if ( (unsigned int)v20 > (unsigned int)LowPart || (unsigned int)v20 > (unsigned int)Options )
  {
    RefsCompleteRequest(a1, Irp, -1073740630);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 74, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226666LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073740630, 0, "Efssup.c", 0xF2Fu);
    return 3221226666LL;
  }
  if ( v20 + 16 <= LowPart
    && v20 + 16 <= (unsigned __int64)v85
    && *(DWORD *)((char *)&Parameters->LowPart + (unsigned int)v20) == 1146378309 )
  {
    if ( *(LONG *)((char *)&Parameters->HighPart + (unsigned int)v20) < 0x10u )
    {
      RefsCompleteRequest(a1, Irp, -1073740630);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 75, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226666LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073740630, 0, "Efssup.c", 0xF49u);
      return 3221226666LL;
    }
    if ( (*((_BYTE *)&Parameters[1].LowPart + (unsigned int)v20) & 1) != 0 )
      v4 = 1;
    v81 = v4;
  }
  v77 = 0;
  if ( (unsigned __int8)(v18 - 1) > 2u )
  {
    RefsCompleteRequest(a1, Irp, -1073741637);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 78, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225659LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741637, 0, "Efssup.c", 0xF6Au);
    return 3221225659LL;
  }
  if ( v16 > HighPart || v19 || !v79 || (v86 = 0, v93 = 0, P = 0, v96 = 0, (unsigned int)LowPart > v85) )
  {
    RefsCompleteRequest(a1, Irp, -1073740630);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 79, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226666LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073740630, 0, "Efssup.c", 0xF73u);
    return 3221226666LL;
  }
  RefsAcquireExclusivePagingIo(a1, v97, 1u);
  RefsAcquireExclusiveScb(a1, v14, 0);
  if ( (*((_DWORD *)v14 + 38) & 0x1000000) == 0 )
    _InterlockedOr((volatile signed __int32 *)v14 + 38, 0x1000000u);
  v21 = *((_WORD *)v14 + 128);
  if ( (v21 & 0x4000) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 80, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226663LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073740633, 0, "Efssup.c", 0xF92u);
    Status = -1073740633;
    goto LABEL_237;
  }
  if ( v4 && v21 >= 0 )
    RefsChangeStreamSparsenessAndBlob(a1, v14, 1u, (v21 & 0x2000) != 0);
  CcFlushCache((PSECTION_OBJECT_POINTERS)(*((_QWORD *)v14 + 31) + 8LL), 0, 0, &Irp->IoStatus);
  RefsNormalizeAndCleanupTransaction(a1, (int *)&Irp->IoStatus.0, v22, v23);
  if ( !CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)(*((_QWORD *)v14 + 31) + 8LL), 0, 0, 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 81, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225499LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741797, 0, "Efssup.c", 0xFA8u);
    Status = -1073741797;
    goto LABEL_237;
  }
  if ( v82.QuadPart > *((_QWORD *)v14 + 4) || v82.QuadPart < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 82, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226664LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073740632, 0, "Efssup.c", 0xFB5u);
    Status = -1073740632;
    goto LABEL_237;
  }
  v77 = 1;
  v24 = 0;
  v83 = 0;
  v25 = 0;
  v26 = v79;
  while ( v25 < v79 )
  {
    v27 = *(&Parameters[3].HighPart + v25);
    if ( v27 )
      v24 += v27;
    else
      v24 += 1 << v118;
    v83 = v24;
    ++v25;
  }
  v77 = 0;
  v28 = v91;
  if ( v91 != v24 )
  {
    if ( (_BYTE)v119 )
    {
      v119 = __PAIR64__((unsigned int)VirtualAddress, v94);
      v29 = __PAIR64__((unsigned int)VirtualAddress, v94);
    }
    else
    {
      v29 = *((_QWORD *)v14 + 5);
    }
    if ( v106.QuadPart + v91 < v29 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 83, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226665LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073740631, 0, "Efssup.c", 0xFE7u);
      Status = -1073740631;
      goto LABEL_237;
    }
    v26 = v79;
  }
  RefsCheckpointCurrentTransaction(a1);
  RefsFreeSnapshotsForFcb(a1, v97);
  v30 = 0;
  LOWORD(v119) = 0;
  v31 = 0;
  while ( 1 )
  {
    if ( v30 >= v26 )
    {
      if ( Status >= 0 )
      {
        v66 = HighPart;
        if ( (struct _SCB *)HighPart != v31 || (unsigned int)v28 < (__int64)v31 )
        {
          v67 = v106;
          v68 = v106.QuadPart + v28;
          RefsSnapshotScb(a1, v14, 0, 0x7FFFFFFFFFFFFFFFLL);
          v69 = v66 + v67.QuadPart;
          *((_QWORD *)v14 + 4) = v66 + v67.QuadPart;
          *((_QWORD *)v14 + 5) = v66 + v67.QuadPart;
          if ( *(_WORD *)v14 == 2053 && *((_QWORD *)v14 + 53) < v69 )
            *((_QWORD *)v14 + 53) = v69;
          if ( v68 < *((_QWORD *)v14 + 5) )
          {
            *((_QWORD *)v14 + 4) = v68;
            *((_QWORD *)v14 + 5) = v68;
            if ( *(_WORD *)v14 == 2053 && *((_QWORD *)v14 + 53) < v68 )
              *((_QWORD *)v14 + 53) = v68;
          }
          RefsWriteFileSizes(a1, v14, 0, 2u, (unsigned __int8)StartingOffset);
          v70 = (struct _FILE_OBJECT *)*((_QWORD *)v14 + 30);
          if ( v70 )
            CcSetFileSizesEx(v70, (PCC_FILE_SIZES)v14 + 1);
        }
      }
      goto LABEL_237;
    }
    v77 = 1;
    v32 = v84;
    if ( (_DWORD)v28 || (v33 = v118, *(_DWORD *)(v84 + 272) > (unsigned int)(1 << v118)) || *((__int16 *)v14 + 128) >= 0 )
    {
      v34 = *(&Parameters[3].HighPart + v30);
      v83 = v34;
      v33 = v118;
    }
    else
    {
      v34 = 0;
      v83 = 0;
    }
    v77 = 0;
    if ( !v34 )
    {
      v50 = 1 << v33;
      v83 = 1 << v33;
      if ( ((v82.LowPart | (1 << v33)) & *(_DWORD *)(v84 + 544)) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            90,
            &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            3221226666LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_176;
        v39 = 4417;
        goto LABEL_175;
      }
      v51 = *((_QWORD *)v14 + 3);
      if ( v51 )
      {
        v52 = *((_QWORD *)v14 + 4);
        if ( v52 != v51 )
          RefsDeleteAllocation(
            a1,
            v14,
            (v52 + *(unsigned int *)(*((_QWORD *)v14 + 18) + 544LL)) >> *(_BYTE *)(*((_QWORD *)v14 + 18) + 552LL),
            0x7FFFFFFFFFFFFFFFLL,
            1u);
      }
      v31 = v86;
      goto LABEL_189;
    }
    if ( !(_DWORD)v28 )
    {
      v50 = v34;
LABEL_189:
      v46 = v84;
      goto LABEL_190;
    }
    v35 = v95 + v34;
    if ( v95 + v34 < v95 )
    {
      v90 = -1;
LABEL_169:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 84, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226666LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_176;
      v39 = 4144;
      goto LABEL_175;
    }
    v36 = v34;
    v37 = (unsigned __int64)v105 + v95;
    VirtualAddress = (PVOID)v37;
    v95 += v34;
    v90 = v35;
    if ( v35 > v85 )
      goto LABEL_169;
    v38 = *(unsigned int *)(v84 + 276);
    if ( v34 % (unsigned int)v38 || v37 % v38 )
    {
      v36 = -(int)v38 & (v38 + v34 - 1);
      if ( v36 < v34 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            85,
            &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            3221226666LL);
        }
        if ( !(_BYTE)RefsStatusDebugEnabled )
          goto LABEL_176;
        v39 = 4170;
LABEL_175:
        RefsStatusDebug(-1073740630, 0, "Efssup.c", v39);
LABEL_176:
        Status = -1073740630;
        goto LABEL_237;
      }
      PoolWithTag = (unsigned __int64)v93;
      if ( !v93 )
        goto LABEL_129;
      if ( v96 < v36 )
      {
        ExFreePoolWithTag(P, 0);
        PoolWithTag = 0;
        v93 = 0;
        v103 = 0;
        P = 0;
        v32 = v84;
      }
      if ( !PoolWithTag )
      {
LABEL_129:
        PoolWithTag = (unsigned __int64)ExAllocatePoolWithTag(
                                          (POOL_TYPE)(PoolType | 0x10),
                                          v36 + *(_DWORD *)(v32 + 276) - 1,
                                          0x30666552u);
        v93 = (void *)PoolWithTag;
        P = (PVOID)PoolWithTag;
        v103 = PoolWithTag;
        v96 = v36;
        v107 = v36;
        if ( PoolWithTag % *(unsigned int *)(v84 + 276) )
        {
          PoolWithTag = -(__int64)*(int *)(v84 + 276) & (*(int *)(v84 + 276) + PoolWithTag - 1);
          v93 = (void *)PoolWithTag;
          v103 = PoolWithTag;
        }
      }
      v77 = 1;
      memmove((void *)PoolWithTag, (const void *)v37, v34);
      v77 = 0;
      v37 = (unsigned __int64)v93;
      memset((char *)v93 + v34, 0, v36 - v34);
      VirtualAddress = (PVOID)v37;
      v32 = v84;
    }
    v41 = IoBuildSynchronousFsdRequest(
            4u,
            *(PDEVICE_OBJECT *)(*(_QWORD *)(v32 + 208) + 8LL),
            (PVOID)v37,
            v36,
            &v82,
            &Event,
            &v113);
    v42 = v41;
    Irpa = v41;
    if ( !v41 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 86, &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225626LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v43 = 4209;
        goto LABEL_139;
      }
      goto LABEL_140;
    }
    if ( VirtualAddress == v93 )
    {
      Mdl = IoAllocateMdl(VirtualAddress, v36, 0, 0, 0);
      v42->MdlAddress = Mdl;
      if ( !Mdl )
      {
        IoFreeIrp(v42);
        Irpa = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            87,
            &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            3221225626LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v43 = 4222;
LABEL_139:
          RefsStatusDebug(-1073741670, 0, "Efssup.c", v43);
        }
LABEL_140:
        Status = -1073741670;
        goto LABEL_237;
      }
      MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
      MmMdlPageContentsState(v42->MdlAddress, 1);
      v42->UserBuffer = 0;
      v42->RequestorMode = 0;
    }
    else
    {
      v41->UserBuffer = VirtualAddress;
      v41->RequestorMode = Irp->RequestorMode;
    }
    v42->Flags |= 5u;
    v45 = v42->Tail.Overlay.CurrentStackLocation;
    v46 = v84;
    v45[-1].DeviceObject = *(PDEVICE_OBJECT *)(*(_QWORD *)(v84 + 208) + 8LL);
    v45[-1].Parameters.Read.ByteOffset = v82;
    v45[-1].Parameters.Read.Length = v34;
    v45[-1].FileObject = FileObject;
    Status = IofCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)(v46 + 208) + 8LL), v42);
    if ( Status == 259 )
    {
      Status = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      if ( !Status )
        Status = v113.Status;
    }
    RefsNormalizeAndCleanupTransaction(a1, &Status, v47, v48);
    Status = RefsWriteRawSetEncryptionForByteRange(a1, v14, v82.QuadPart, v34);
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          89,
          &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
          (unsigned int)Status);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v49 = 4332;
        goto LABEL_161;
      }
      goto LABEL_237;
    }
    v31 = (struct _SCB *)((char *)v86 + v34);
    v86 = v31;
    v111 = v31;
    v82.QuadPart += v34;
    if ( v34 >= 1 << v118 || HighPart <= v91 )
      v50 = 0;
    else
      v50 = *((__int16 *)v14 + 128) >= 0 ? HighPart - v91 : (1 << v118) - v34;
LABEL_190:
    if ( !v50 )
    {
      v64 = 0;
      goto LABEL_216;
    }
    v94 = 0;
    v104 = 0;
    v53 = *(unsigned int *)(v46 + 548);
    v54 = v82.LowPart + *(_DWORD *)(v46 + 544);
    v55 = (unsigned int)v53 & (v54 + v50);
    v56 = *((_QWORD *)v14 + 18);
    v57 = *(_BYTE *)(v56 + 552);
    v58 = *((_QWORD *)v14 + 3);
    v59 = *(unsigned int *)(v56 + 544);
    v60 = (v58 + v59) >> v57;
    VirtualAddress = (PVOID)v60;
    v61 = (v59 + ((unsigned int)v53 & v54)) >> v57;
    v104 = v61;
    v62 = (v59 + v55) >> v57;
    if ( *((__int16 *)v14 + 128) < 0 )
      break;
    if ( v58 < v55 )
      goto LABEL_197;
LABEL_210:
    v64 = v50;
    v65 = v50 + v82.QuadPart;
    RefsSnapshotScb(a1, v14, 0, v53);
    if ( v65 > *((_QWORD *)v14 + 4) )
    {
      *((_QWORD *)v14 + 4) = v65;
      *((_QWORD *)v14 + 5) = v65;
      if ( *(_WORD *)v14 == 2053 && *((_QWORD *)v14 + 53) < v65 )
        *((_QWORD *)v14 + 53) = v65;
    }
    RefsWriteFileSizes(a1, v14, 0, 2u, (unsigned __int8)StartingOffset);
    v110 = *((_QWORD *)v14 + 31) + 8LL;
    CcSetFileSizesEx((PFILE_OBJECT)(&v73 + 33), (PCC_FILE_SIZES)v14 + 1);
    RefsCheckpointCurrentTransaction(a1);
    RefsReleaseSharedResources(a1);
    RefsFreeSnapshotsForFcb(a1, v97);
    v31 = (struct _SCB *)((char *)v86 + v64);
    v86 = v31;
    v111 = v31;
LABEL_216:
    v82.QuadPart += v64;
    v30 = v119 + 1;
    LOWORD(v119) = v119 + 1;
    Parameters = v105;
    v28 = v91;
    v26 = v79;
  }
  *(_QWORD *)&v114 = (v59 + ((unsigned int)v53 & v54)) >> v57;
  *((_QWORD *)&v114 + 1) = v62 - v61 + 1;
  v115[0] = v114;
  if ( (unsigned __int8)RefsIsRangeAllocated(a1, v14, v115, &v94)
    && v94 == (__int64)(v50 + (unsigned __int64)*(unsigned int *)(*((_QWORD *)v14 + 18) + 544LL)) >> *(_BYTE *)(*((_QWORD *)v14 + 18) + 552LL) )
  {
    goto LABEL_210;
  }
  v60 = (__int64)VirtualAddress;
LABEL_197:
  if ( *((__int16 *)v14 + 128) >= 0 )
  {
    if ( v60 > v61 )
      v61 = v60;
    v104 = v61;
  }
  if ( v61 > v62 )
    goto LABEL_210;
  RefsDeleteAllocation(a1, v14, v61, 0x7FFFFFFFFFFFFFFFLL, 1u);
  v63 = v62 - v61 + 1;
  v75 = 0;
  LODWORD(StartingOffset) = 0;
  RefsAddAllocation(a1, v14, v61, v63);
  if ( *((__int16 *)v14 + 128) < 0 )
    goto LABEL_210;
  Status = RefsWriteRawSetEncryptionForByteRange(a1, v14, v61 << *(_BYTE *)(v84 + 552), v63 << *(_BYTE *)(v84 + 552));
  if ( Status >= 0 )
    goto LABEL_210;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      91,
      &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
      (unsigned int)Status);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v49 = 4528;
LABEL_161:
    RefsStatusDebug(Status, 0, "Efssup.c", v49);
  }
LABEL_237:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    v71 = 0;
    v72 = Status < 0 ? BYTE1(WPP_GLOBAL_Control->Timer) < 4u : BYTE1(WPP_GLOBAL_Control->Timer) < 5u;
    LOBYTE(v71) = !v72;
    if ( v71 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        94,
        &WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
        (unsigned int)Status);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(Status, 0, "Efssup.c", 0x1211u);
  if ( P )
    ExFreePoolWithTag(P, 0);
  RefsCompleteRequest(a1, Irp, Status);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1402a7120  mov     r11, rsp
0x1402a7123  mov     [r11+10h], rdx
0x1402a7127  mov     [r11+8], rcx
0x1402a712b  push    rbx
0x1402a712c  push    rsi
0x1402a712d  push    rdi
0x1402a712e  push    r12
0x1402a7130  push    r13
0x1402a7132  push    r14
0x1402a7134  push    r15
0x1402a7136  sub     rsp, 190h
0x1402a713d  mov     rsi, rdx
0x1402a7140  mov     r14, rcx
0x1402a7143  xor     edi, edi
0x1402a7145  mov     qword ptr [rsp+1C8h+var_158], rdi
0x1402a714a  mov     [r11-0A8h], rdi
0x1402a7151  mov     [rsp+1C8h+var_E0], edi
0x1402a7158  mov     [rsp+1C8h+var_DC], edi
0x1402a715f  mov     [r11-148h], rdi
0x1402a7166  mov     [r11-0F8h], rdi
0x1402a716d  mov     [r11-138h], rdi
0x1402a7174  mov     [r11+20h], rdi
0x1402a7178  mov     [rsp+1C8h+var_120], edi
0x1402a717f  mov     [rsp+1C8h+var_124], di
0x1402a7187  mov     [rsp+1C8h+var_168], dil
0x1402a718c  mov     [rsp+1C8h+var_15E], dil
0x1402a7191  xorps   xmm0, xmm0
0x1402a7194  xor     eax, eax
0x1402a7196  movups  xmmword ptr [rsp+1C8h+Event.Header], xmm0
0x1402a719e  mov     [r11-78h], rax
0x1402a71a2  movups  xmmword ptr [r11-70h], xmm0
0x1402a71a7  movzx   r12d, dil
0x1402a71ab  mov     [rsp+1C8h+var_15D], r12b
0x1402a71b0  mov     [rsp+1C8h+Status], edi
0x1402a71b4  mov     [r11+18h], rdi
0x1402a71b8  mov     ecx, cs:Feature_ReFS_EFS__private_featureState
0x1402a71be  mov     [r11+18h], ecx
0x1402a71c2  lea     r15d, [rdi+1]
0x1402a71c6  test    cl, 10h
0x1402a71c9  jnz     short loc_1402A7206
0x1402a71cb  mov     rax, [r11+18h]
0x1402a71cf  mov     [r11+18h], rax
0x1402a71d3  or      ecx, r15d
0x1402a71d6  mov     [r11+18h], ecx
0x1402a71da  lea     ebx, [rdi+3]
0x1402a71dd  mov     r8d, ebx
0x1402a71e0  mov     rdx, [r11+18h]
0x1402a71e4  lea     rcx, Feature_ReFS_EFS__private_descriptor
0x1402a71eb  call    wil_details_FeatureReporting_ReportUsageToService
0x1402a71f0  lea     r8, Feature_ReFS_EFS__private_descriptor
0x1402a71f7  mov     edx, ebx
0x1402a71f9  mov     rcx, [rsp+1C8h+arg_10]
0x1402a7201  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x1402a7206  or      [r14+8], r15
0x1402a720a  xor     r8d, r8d; State
0x1402a720d  mov     edx, r15d; Type
0x1402a7210  lea     rcx, [rsp+1C8h+Event]; Event
0x1402a7218  call    cs:__imp_KeInitializeEvent
0x1402a721f  nop     dword ptr [rax+rax+00h]
0x1402a7224  mov     rbx, [rsi+0B8h]
0x1402a722b  mov     rax, [rbx+30h]
0x1402a722f  mov     [rsp+1C8h+var_A0], rax
0x1402a7237  mov     byte ptr [rsp+1C8h+IoStatusBlock], r15b
0x1402a723c  lea     rcx, [rsp+1C8h+arg_18]
0x1402a7244  mov     [rsp+1C8h+var_1A0], rcx
0x1402a7249  lea     rcx, [rsp+1C8h+var_138]
0x1402a7251  mov     [rsp+1C8h+StartingOffset], rcx; unsigned __int8
0x1402a7256  lea     r9, [rsp+1C8h+var_F8]
0x1402a725e  lea     r8, [rsp+1C8h+var_148]
0x1402a7266  mov     rdx, rax
0x1402a7269  mov     rcx, r14
0x1402a726c  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1402a7271  cmp     al, 2
0x1402a7273  jz      short loc_1402A72ED
0x1402a7275  mov     r15d, 0C000000Dh
0x1402a727b  mov     r8d, r15d; Status
0x1402a727e  mov     rdx, rsi; Irp
0x1402a7281  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402a7284  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402a7289  lea     rbx, WPP_GLOBAL_Control
0x1402a7290  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a7297  cmp     rcx, rbx
0x1402a729a  jz      short loc_1402A72C3
0x1402a729c  test    dword ptr [rcx+2Ch], 100h
0x1402a72a3  jz      short loc_1402A72C3
0x1402a72a5  cmp     byte ptr [rcx+29h], 4
0x1402a72a9  jb      short loc_1402A72C3
0x1402a72ab  mov     edx, 45h ; 'E'
0x1402a72b0  mov     r9d, r15d
0x1402a72b3  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x1402a72ba  mov     rcx, [rcx+18h]
0x1402a72be  call    WPP_SF_d
0x1402a72c3  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a72c9  test    cl, cl
0x1402a72cb  jz      short loc_1402A72E4
0x1402a72cd  mov     r9d, 0EA5h; unsigned int
0x1402a72d3  lea     r8, aEfssupC; "Efssup.c"
0x1402a72da  xor     edx, edx; struct _IRP_CONTEXT *
0x1402a72dc  mov     ecx, r15d; Status
0x1402a72df  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402a72e4  mov     eax, r15d
0x1402a72e7  jmp     loc_1402A8A2E
0x1402a72ed  mov     r13, [rsp+1C8h+var_148]
0x1402a72f5  test    dword ptr [r13+18h], 2000000h
0x1402a72fd  jz      short loc_1402A7362
0x1402a72ff  mov     r15d, 0C00000A2h
0x1402a7305  mov     r8d, r15d; Status
0x1402a7308  mov     rdx, rsi; Irp
0x1402a730b  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402a730e  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402a7313  lea     rbx, WPP_GLOBAL_Control
0x1402a731a  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a7321  cmp     rcx, rbx
0x1402a7324  jz      short loc_1402A734D
0x1402a7326  test    dword ptr [rcx+2Ch], 100h
0x1402a732d  jz      short loc_1402A734D
0x1402a732f  cmp     byte ptr [rcx+29h], 4
0x1402a7333  jb      short loc_1402A734D
0x1402a7335  mov     edx, 46h ; 'F'
0x1402a733a  mov     r9d, r15d
0x1402a733d  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x1402a7344  mov     rcx, [rcx+18h]
0x1402a7348  call    WPP_SF_d
0x1402a734d  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a7353  test    cl, cl
0x1402a7355  jz      short loc_1402A72E4
0x1402a7357  mov     r9d, 0EAFh
0x1402a735d  jmp     loc_1402A72D3
0x1402a7362  mov     rdx, [rsp+1C8h+arg_18]
0x1402a736a  mov     eax, [rdx+54h]
0x1402a736d  mov     [r14+278h], eax
0x1402a7374  movzx   r8d, word ptr [rdx+58h]
0x1402a7379  test    r8b, 12h
0x1402a737d  jnz     loc_1402A7480
0x1402a7383  lea     rbx, WPP_GLOBAL_Control
0x1402a738a  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a7391  cmp     rcx, rbx
0x1402a7394  jz      loc_1402A7420
0x1402a739a  test    dword ptr [rcx+2Ch], 10000h
0x1402a73a1  jz      short loc_1402A7420
0x1402a73a3  cmp     byte ptr [rcx+29h], 2
0x1402a73a7  jb      short loc_1402A7420
0x1402a73a9  mov     r10, [rsp+1C8h+var_F8]
0x1402a73b1  mov     r9, [r10+58h]
0x1402a73b5  mov     r11, gs:188h
0x1402a73be  mov     eax, r8d
0x1402a73c1  lea     rcx, [rdx+10h]
0x1402a73c5  lea     r8, [r13+1808h]
0x1402a73cc  mov     edx, 47h ; 'G'
0x1402a73d1  mov     [rsp+1C8h+var_170], eax
0x1402a73d5  mov     [rsp+1C8h+var_178], rcx
0x1402a73da  mov     rax, [r10+150h]
0x1402a73e1  mov     [rsp+1C8h+var_180], rax
0x1402a73e6  mov     rax, [r9+0F8h]
0x1402a73ed  mov     [rsp+1C8h+var_188], rax
0x1402a73f2  mov     rax, [r9+100h]
0x1402a73f9  mov     [rsp+1C8h+var_190], rax
0x1402a73fe  mov     [rsp+1C8h+IoStatusBlock], r10
0x1402a7403  mov     [rsp+1C8h+var_1A0], r8
0x1402a7408  mov     [rsp+1C8h+StartingOffset], r13
0x1402a740d  mov     r9, r11
0x1402a7410  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a7417  mov     rcx, [rcx+18h]
0x1402a741b  call    WPP_SF_qqZqiiiZD
0x1402a7420  mov     r15d, 0C0000022h
0x1402a7426  mov     r8d, r15d; Status
0x1402a7429  mov     rdx, rsi; Irp
0x1402a742c  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402a742f  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402a7434  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a743b  cmp     rcx, rbx
0x1402a743e  jz      short loc_1402A7467
0x1402a7440  test    dword ptr [rcx+2Ch], 100h
0x1402a7447  jz      short loc_1402A7467
0x1402a7449  cmp     byte ptr [rcx+29h], 4
0x1402a744d  jb      short loc_1402A7467
0x1402a744f  mov     edx, 48h ; 'H'
0x1402a7454  mov     r9d, r15d
0x1402a7457  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x1402a745e  mov     rcx, [rcx+18h]
0x1402a7462  call    WPP_SF_d
0x1402a7467  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a746d  test    cl, cl
0x1402a746f  jz      loc_1402A72E4
0x1402a7475  mov     r9d, 0ECDh
0x1402a747b  jmp     loc_1402A72D3
0x1402a7480  mov     ecx, [rbx+10h]
0x1402a7483  mov     [rsp+1C8h+var_140], ecx
0x1402a748a  cmp     ecx, 20h ; ' '
0x1402a748d  jnb     short loc_1402A74F6
0x1402a748f  mov     r15d, 0C0000023h
0x1402a7495  mov     r8d, r15d; Status
0x1402a7498  mov     rdx, rsi; Irp
0x1402a749b  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402a749e  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402a74a3  lea     rbx, WPP_GLOBAL_Control
0x1402a74aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a74b1  cmp     rcx, rbx
0x1402a74b4  jz      short loc_1402A74DD
0x1402a74b6  test    dword ptr [rcx+2Ch], 100h
0x1402a74bd  jz      short loc_1402A74DD
0x1402a74bf  cmp     byte ptr [rcx+29h], 4
0x1402a74c3  jb      short loc_1402A74DD
0x1402a74c5  mov     edx, 49h ; 'I'
0x1402a74ca  mov     r9d, r15d
0x1402a74cd  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x1402a74d4  mov     rcx, [rcx+18h]
0x1402a74d8  call    WPP_SF_d
0x1402a74dd  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402a74e3  test    cl, cl
0x1402a74e5  jz      loc_1402A72E4
0x1402a74eb  mov     r9d, 0EDEh
0x1402a74f1  jmp     loc_1402A72D3
0x1402a74f6  mov     r13, [rbx+20h]
0x1402a74fa  mov     [rsp+1C8h+var_C0], r13
0x1402a7502  mov     rsi, [rsp+1C8h+var_138]
0x1402a750a  cmp     dword ptr [rbx-40h], 0FFFFFFFFh
0x1402a750e  jnz     short loc_1402A7537
0x1402a7510  mov     dword ptr [rsp+1C8h+var_108], edi
0x1402a7517  mov     dword ptr [rsp+1C8h+VirtualAddress], edi
0x1402a751e  mov     byte ptr [rsp+1C8h+arg_18], dil
0x1402a7526  mov     [rbx-40h], edi
0x1402a7529  mov     eax, [rsi+28h]
0x1402a752c  mov     [rbx-38h], eax
0x1402a752f  mov     eax, [rsi+2Ch]
0x1402a7532  mov     [rbx-30h], eax
0x1402a7535  jmp     short loc_1402A7553
0x1402a7537  mov     byte ptr [rsp+1C8h+arg_18], r15b
0x1402a753f  mov     eax, [rbx-38h]
0x1402a7542  mov     dword ptr [rsp+1C8h+var_108], eax
0x1402a7549  mov     eax, [rbx-30h]
0x1402a754c  mov     dword ptr [rsp+1C8h+VirtualAddress], eax
0x1402a7553  mov     [rsp+1C8h+var_168], r15b
0x1402a7558  mov     rbx, [rsp+1C8h+arg_8]
0x1402a7560  cmp     [rbx+40h], dil
0x1402a7564  jz      short loc_1402A7582
0x1402a7566  mov     rdx, rcx; Length
0x1402a7569  mov     r8d, r15d; Alignment
0x1402a756c  mov     rcx, r13; Address
0x1402a756f  call    cs:__imp_ProbeForRead
0x1402a7576  nop     dword ptr [rax+rax+00h]
0x1402a757b  mov     ecx, [rsp+1C8h+var_140]
0x1402a7582  mov     r11d, [r13+8]
0x1402a7586  mov     [rsp+1C8h+var_100], r11d
0x1402a758e  mov     [rsp+1C8h+var_120], r11d
0x1402a7596  mov     r10d, [r13+10h]
0x1402a759a  mov     [rsp+1C8h+var_11C], r10d
0x1402a75a2  mov     [rsp+1C8h+var_E0], r10d
0x1402a75aa  mov     eax, [r13+0Ch]
0x1402a75ae  mov     [rsp+1C8h+var_118], eax
0x1402a75b5  mov     [rsp+1C8h+var_DC], eax
0x1402a75bc  movzx   r8d, word ptr [r13+1Ah]
0x1402a75c1  mov     [rsp+1C8h+var_160], r8w
0x1402a75c7  mov     [rsp+1C8h+var_124], r8w
0x1402a75d0  mov     dl, [r13+19h]
0x1402a75d4  mov     [rsp+1C8h+var_128], dl
0x1402a75db  mov     rax, [r13+0]
0x1402a75df  mov     [rsp+1C8h+var_B8], rax
0x1402a75e7  mov     qword ptr [rsp+1C8h+var_158], rax
0x1402a75ec  mov     [rsp+1C8h+var_A8], rax
0x1402a75f4  mov     al, [r13+16h]
0x1402a75f8  mov     byte ptr [rsp+1C8h+arg_10], al
0x1402a75ff  mov     [rsp+1C8h+var_15E], al
0x1402a7603  movzx   r9d, word ptr [r13+14h]
0x1402a7608  mov     [rsp+1C8h+var_E8], r9w
0x1402a7611  lea     eax, ds:1Ch[r8*4]
0x1402a7619  cmp     eax, r11d
0x1402a761c  ja      loc_1402A88CD
0x1402a7622  cmp     eax, ecx
0x1402a7624  ja      loc_1402A88CD
0x1402a762a  mov     ecx, eax
0x1402a762c  lea     r8, [rax+10h]
0x1402a7630  cmp     r8, r11
0x1402a7633  ja      loc_1402A76EA
0x1402a7639  mov     eax, [rsp+1C8h+var_140]
0x1402a7640  cmp     r8, rax
0x1402a7643  ja      loc_1402A76EA
0x1402a7649  mov     eax, cs:dword_140209944
0x1402a764f  cmp     [rcx+r13], eax
0x1402a7653  jnz     loc_1402A76EA
0x1402a7659  cmp     dword ptr [rcx+r13+4], 10h
0x1402a765f  jnb     short loc_1402A76DC
0x1402a7661  mov     r8d, 0C00004AAh; Status
0x1402a7667  mov     rdx, rbx; Irp
0x1402a766a  mov     rcx, r14; struct _IRP_CONTEXT *
0x1402a766d  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402a7672  lea     rbx, WPP_GLOBAL_Control
0x1402a7679  mov     rcx, cs:WPP_GLOBAL_Control
0x1402a7680  cmp     rcx, rbx
0x1402a7683  jz      short loc_1402A76AF
0x1402a7685  test    dword ptr [rcx+2Ch], 100h
0x1402a768c  jz      short loc_1402A76AF
0x1402a768e  cmp     byte ptr [rcx+29h], 4
0x1402a7692  jb      short loc_1402A76AF
0x1402a7694  mov     edx, 4Bh ; 'K'
0x1402a7699  mov     r9d, 0C00004AAh
0x1402a769f  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x1402a76a6  mov     rcx, [rcx+18h]
0x1402a76aa  call    WPP_SF_d
0x1402a76af  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
  ... truncated ...
```
