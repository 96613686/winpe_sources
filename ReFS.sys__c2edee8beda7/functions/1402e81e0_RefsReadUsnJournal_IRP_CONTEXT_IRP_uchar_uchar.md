# RefsReadUsnJournal(_IRP_CONTEXT *,_IRP *,uchar,uchar)

- ea: `0x1402e81e0`
- end: `0x1402e944c`
- name: `?RefsReadUsnJournal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@EE@Z`
- size: `4716`
- prototype: `__int64 __usercall@<rax>(struct _IRP_CONTEXT *@<rcx>, PIRP Irp@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>)`
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140323dd8`
- `0x140334054`

## callees

- `0x14000cf40`
- `0x14000e0e0`
- `0x140076ad0`
- `0x14007cdb0`
- `0x140085570`
- `0x1400862c0`
- `0x14008d160`
- `0x140090c50`
- `0x1400a76c8`
- `0x1400d0fd8`
- `0x1400deb90`
- `0x1401f3fc0`
- `0x1401f3ff0`
- `0x1401f4100`
- `0x1401f4400`
- `0x1402e81e0`
- `0x1402ea1b0`
- `0x14031def0`
- `0x14031f9c0`
- `0x14032720c`
- `0x140327840`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1402e941c`
- `ntoskrnl!ExRaiseStatus` at `0x1402e941c`
- `ntoskrnl!CcUnpinData` at `0x1402e8ca8`
- `ntoskrnl!CcUnpinData` at `0x1402e906c`
- `ntoskrnl!CcUnpinData` at `0x1402e9280`
- `ntoskrnl!CcUnpinData` at `0x1403495e9`
- `ntoskrnl!CcUnpinData` at `0x1402e8ca8`
- `ntoskrnl!CcUnpinData` at `0x1402e906c`
- `ntoskrnl!CcUnpinData` at `0x1402e9280`
- `ntoskrnl!CcUnpinData` at `0x1403495e9`
- `ntoskrnl!CcMapData` at `0x1402e8c39`
- `ntoskrnl!CcMapData` at `0x1402e8c39`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1402e827a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x1402e827a`
- `ntoskrnl!ProbeForRead` at `0x1402e8496`
- `ntoskrnl!ProbeForRead` at `0x1402e8496`
- `ntoskrnl!ProbeForWrite` at `0x1402e84bb`
- `ntoskrnl!ProbeForWrite` at `0x1402e84bb`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402e9323`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402e9323`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e8ce0`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e92b1`
- `ntoskrnl!ExReleaseFastResource` at `0x140349628`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e8ce0`
- `ntoskrnl!ExReleaseFastResource` at `0x1402e92b1`
- `ntoskrnl!ExReleaseFastResource` at `0x140349628`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e852c`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x1402e852c`

## pseudocode

```c
__int64 __fastcall RefsReadUsnJournal(struct _IRP_CONTEXT *a1, PIRP Irp, char a3, char a4)
{
  PIRP v6; // r13
  struct _IRP_CONTEXT *v7; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int v9; // edx
  NTSTATUS v10; // ebx
  __int64 v12; // rax
  char v13; // r12
  struct _IRP_CONTEXT *v14; // rcx
  unsigned int v15; // r8d
  __int64 v16; // r8
  _WORD *v17; // r9
  bool v18; // zf
  struct _VCB *v19; // r15
  int v20; // ecx
  unsigned int v21; // r9d
  unsigned int Options; // eax
  unsigned int v23; // r9d
  size_t v24; // r8
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rdx
  unsigned int Length; // r14d
  unsigned int v27; // r14d
  _WORD *v28; // r12
  __int64 v29; // rdx
  bool v30; // sf
  unsigned int v31; // r9d
  int v32; // edx
  int v33; // eax
  __int64 v34; // r14
  __int64 v35; // r14
  char *v36; // rcx
  __int64 v37; // rdx
  bool v38; // r14
  unsigned int *v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r8
  unsigned int v42; // r10d
  int v43; // eax
  int v44; // r14d
  unsigned int v45; // r14d
  char *v46; // rax
  char v47; // r11
  void *v48; // rcx
  int v49; // r14d
  char v50; // al
  __int64 v51; // rax
  int v52; // eax
  IRP *v53; // rdx
  bool v54; // [rsp+44h] [rbp-164h]
  unsigned __int8 v55; // [rsp+49h] [rbp-15Fh]
  char v56[8]; // [rsp+50h] [rbp-158h] BYREF
  char v57; // [rsp+58h] [rbp-150h]
  int v58; // [rsp+5Ch] [rbp-14Ch]
  PVOID Buffer; // [rsp+60h] [rbp-148h] BYREF
  PIRP Irpa; // [rsp+68h] [rbp-140h]
  int v61; // [rsp+70h] [rbp-138h]
  unsigned int v62; // [rsp+74h] [rbp-134h]
  __int64 v63; // [rsp+78h] [rbp-130h]
  char v64; // [rsp+80h] [rbp-128h]
  PVOID Bcb; // [rsp+88h] [rbp-120h] BYREF
  struct _VCB *v66; // [rsp+90h] [rbp-118h] BYREF
  _WORD *v67; // [rsp+98h] [rbp-110h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-108h]
  __int64 v69; // [rsp+A8h] [rbp-100h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+B0h] [rbp-F8h] BYREF
  struct _IRP_CONTEXT *v71; // [rsp+B8h] [rbp-F0h]
  __int64 v72; // [rsp+C0h] [rbp-E8h] BYREF
  _WORD *v73; // [rsp+C8h] [rbp-E0h]
  __int64 v74; // [rsp+D0h] [rbp-D8h]
  __int64 v75[10]; // [rsp+E0h] [rbp-C8h] BYREF
  __int128 v76; // [rsp+130h] [rbp-78h] BYREF
  __int128 v77; // [rsp+140h] [rbp-68h]
  __int128 v78; // [rsp+150h] [rbp-58h] BYREF

  v56[1] = a4;
  v57 = a3;
  v6 = Irp;
  Irpa = Irp;
  v7 = a1;
  v71 = a1;
  Buffer = 0;
  Bcb = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v66 = 0;
  FileOffset.QuadPart = 0;
  v67 = 0;
  memset(v75, 0, 0x48u);
  ExInitializeFastOwnerEntry(v75);
  CurrentStackLocation = v6->Tail.Overlay.CurrentStackLocation;
  RefsDecodeFileObject(v7, CurrentStackLocation->FileObject, &v66, &v72, &FileOffset, &v67, 1);
  if ( !a4 && (!v67 || (v67[44] & 0x200) == 0 && (v6->RequestorMode || CurrentStackLocation->MinorFunction != 4)) )
  {
    v10 = -1073741790;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v7, v6, -1073741790);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790, 0, "UsnSup.c", 0x47Cu);
    return (unsigned int)v10;
  }
  v54 = 0;
  v55 = 0;
  LOBYTE(v9) = 1;
  v61 = v9;
  if ( a3 )
  {
    LOBYTE(v9) = (*((_BYTE *)v7 + 8) & 1) != 0;
    v61 = v9;
  }
  v12 = *((_QWORD *)v7 + 1);
  v72 = (v12 & 1) == 0;
  v74 = v72;
  *((_QWORD *)v7 + 1) = v12 | 1;
  v13 = RefsEffectiveMode(v6, CurrentStackLocation);
  v10 = RefsLockUserBuffer(v14, v6, IoWriteAccess, CurrentStackLocation->Parameters.Read.Length);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids,
        (unsigned int)v10);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(v10, v7, "UsnSup.c", 0x4A3u);
    RefsRaiseStatusInternal(v7, v10, v15);
  }
  v17 = RefsMapUserBuffer(v6);
  v67 = v17;
  if ( v6->RequestorMode )
  {
    if ( a3 )
    {
      ProbeForRead(
        CurrentStackLocation->Parameters.CreatePipe.Parameters,
        CurrentStackLocation->Parameters.Create.Options,
        4u);
      v17 = v67;
    }
    if ( !v6->MdlAddress )
      ProbeForWrite(v17, CurrentStackLocation->Parameters.Read.Length, 4u);
  }
  else if ( CurrentStackLocation->Parameters.CreatePipe.Parameters != (PNAMED_PIPE_CREATE_PARAMETERS)(((unsigned __int64)&CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType + 3) & 0xFFFFFFFFFFFFFFFCuLL)
         || !v6->MdlAddress && v17 != (_WORD *)(((unsigned __int64)v17 + 3) & 0xFFFFFFFFFFFFFFFCuLL) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v10 = -1073741811;
    }
    else
    {
      v10 = -1073741811;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811, 0, "UsnSup.c", 0x4BFu);
    v19 = v66;
    goto LABEL_214;
  }
  v18 = a3 == 0;
  v19 = v66;
  if ( !v18 )
    v55 = RefsAcquireSharedVcb(v7, v66, 1u);
  LOBYTE(v16) = 1;
  ExAcquireFastResourceShared((char *)v19 + 1208, v75, v16);
  *((_DWORD *)v7 + 1) |= 0x2000u;
  v54 = 1;
  v20 = *((_DWORD *)v19 + 6);
  if ( (v20 & 0x100000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221226167LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_41;
    v21 = 1238;
LABEL_40:
    RefsStatusDebug(-1073741129, 0, "UsnSup.c", v21);
LABEL_41:
    v10 = -1073741129;
    goto LABEL_223;
  }
  if ( !*((_QWORD *)v19 + 5) || (v20 & 0x80000) == 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v10 = -1073741128;
    }
    else
    {
      v10 = -1073741128;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221226168LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_214;
    v23 = 1247;
    goto LABEL_213;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options >= 0x28 )
  {
    v24 = 48;
    if ( Options != 48 )
    {
      DWORD2(v78) = 131074;
      v24 = 40;
    }
    Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
    if ( v13 )
      RtlCopyFromUser(&v76, Parameters, v24);
    else
      RtlCopyVolatileMemory(&v76, Parameters, v24);
    if ( (_QWORD)v78 != *((_QWORD *)v19 + 113) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741811;
      }
      else
      {
        v10 = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v23 = 1290;
      goto LABEL_213;
    }
    if ( WORD4(v78) > WORD5(v78) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741811;
      }
      else
      {
        v10 = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v23 = 1299;
      goto LABEL_213;
    }
    if ( WORD4(v78) > 3u || WORD5(v78) < 2u )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741811;
      }
      else
      {
        v10 = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v23 = 1308;
      goto LABEL_213;
    }
    Length = CurrentStackLocation->Parameters.Read.Length;
    if ( Length < 8 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741789;
      }
      else
      {
        v10 = -1073741789;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221225507LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v23 = 1318;
      goto LABEL_213;
    }
    v27 = Length - 8;
    *(_DWORD *)&v56[4] = v27;
    v28 = v67 + 4;
    v73 = v67 + 4;
    v62 = 8;
    if ( v55 )
    {
      RefsReleaseVcb(v7, v19);
      v55 = 0;
    }
    if ( (*(_DWORD *)(*((_QWORD *)v19 + 5) + 300LL) & 0x4000) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741202;
      }
      else
      {
        v10 = -1073741202;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221226094LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v23 = 1340;
      goto LABEL_213;
    }
    v29 = v76;
    v30 = (__int64)v76 < 0;
    if ( !(_QWORD)v76 )
    {
      v29 = *((_QWORD *)v19 + 115);
      *(_QWORD *)&v76 = v29;
      v30 = v29 < 0;
    }
    if ( v30 || *((_QWORD *)&v77 + 1) > 0x7FFFFFFFFFFFFFFFuLL || v29 + *((_QWORD *)&v77 + 1) < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741811;
      }
      else
      {
        v10 = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221225485LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_214;
      v23 = 1362;
      goto LABEL_213;
    }
    while ( 1 )
    {
      if ( v29 >= *((_QWORD *)v19 + 116) )
      {
        if ( (*((_DWORD *)v19 + 6) & 0x2000000) != 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v10 = -1073741662;
          }
          else
          {
            v10 = -1073741662;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              29,
              WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids,
              3221225634LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_223;
          v31 = 1385;
          goto LABEL_108;
        }
        if ( !*((_QWORD *)&v77 + 1) )
          goto LABEL_191;
        v32 = (unsigned __int8)v61;
        if ( Irpa != *((PIRP *)v7 + 9) )
          v32 = 0;
        v61 = v32;
        v64 = v32;
        v68 = *((_QWORD *)v19 + 5);
        v33 = RefsWaitForUsn((int)v7, Irpa, (int)v19, v56[1], v32, (__int64)&v76, (__int64)v75);
        v10 = v33;
        if ( !(_BYTE)v61 )
        {
          if ( v33 == 259 || v33 == -1073741536 || v33 == -1073741129 )
            v54 = Irpa != *((PIRP *)v7 + 9);
          goto LABEL_223;
        }
        if ( v33 < 0 )
        {
LABEL_223:
          v38 = v54;
LABEL_224:
          v6 = Irpa;
          goto LABEL_225;
        }
        if ( v68 != *((_QWORD *)v19 + 5) )
        {
          if ( (*((_DWORD *)v19 + 6) & 0x100000) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                30,
                WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids,
                3221226167LL);
            }
            if ( !(_BYTE)RefsStatusDebugEnabled )
              goto LABEL_41;
            v21 = 1451;
            goto LABEL_40;
          }
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v10 = -1073741128;
          }
          else
          {
            v10 = -1073741128;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              31,
              WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids,
              3221226168LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_223;
          v31 = 1453;
LABEL_108:
          RefsStatusDebug(v10, 0, "UsnSup.c", v31);
          goto LABEL_223;
        }
        v29 = v76;
      }
      if ( v29 < *((_QWORD *)v19 + 115) )
      {
        *(_QWORD *)&v76 = *((_QWORD *)v19 + 115);
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v10 = -1073741105;
        }
        else
        {
          v10 = -1073741105;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            32,
            WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids,
            3221226191LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741105, 0, "UsnSup.c", 0x5D1u);
        v29 = v76;
LABEL_191:
        v6 = Irpa;
        Irpa->IoStatus.Information = v62;
        *(_QWORD *)v67 = v29;
        goto LABEL_214;
      }
LABEL_144:
      if ( !v27 )
        goto LABEL_191;
      v34 = *((_QWORD *)v19 + 116);
      if ( v29 < v34 )
        break;
      v27 = *(_DWORD *)&v56[4];
      if ( !*(_DWORD *)&v56[4] || v62 != 8 )
        goto LABEL_191;
    }
    FileOffset.QuadPart = 0;
    v56[0] = 0;
    v69 = 0;
    v35 = v34 - v29;
    v63 = v35;
    if ( v35 > 0x40000 - ((unsigned int)v29 & 0x3FFFF) )
      v35 = 0x40000 - ((unsigned int)v29 & 0x3FFFF);
    v68 = v35;
    v63 = v35;
    FileOffset.QuadPart = RefsFileOffsetFromUsn(v19, v29);
    CcMapData(*(PFILE_OBJECT *)(*((_QWORD *)v19 + 5) + 240LL), &FileOffset, v35, 0x11u, &Bcb, &Buffer);
    LODWORD(v36) = (_DWORD)Buffer;
    LODWORD(v37) = v76;
LABEL_149:
    if ( !(unsigned __int8)RefsValidateUsnPage(
                             (_DWORD)v7,
                             (unsigned int)v36 & 0xFFFFF000,
                             (unsigned int)v37 & 0xFFFFF000,
                             (unsigned int)&v76,
                             *((_QWORD *)v19 + 116),
                             (__int64)v56,
                             (__int64)&v69) )
    {
      CcUnpinData(Bcb);
      Bcb = 0;
      *((_DWORD *)v7 + 1) &= 0xFFFFCFFF;
      ExReleaseFastResource((char *)v19 + 1208, v75);
      v38 = 0;
      v10 = RefsRepairUsnJournal(v7, (__int64)&v78, v57, (__int64)v56, (__int64)&v69);
      if ( v10 < 0 )
        goto LABEL_224;
      v54 = 1;
      v29 = v76;
      v27 = *(_DWORD *)&v56[4];
      goto LABEL_144;
    }
    if ( !v56[0] )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v10 = -1073741811;
      }
      else
      {
        v10 = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221225485LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v31 = 1596;
        goto LABEL_108;
      }
      goto LABEL_223;
    }
    v39 = (unsigned int *)Buffer;
    v40 = v76;
    v41 = v69;
    while ( 1 )
    {
      if ( v40 >= v41 )
      {
        if ( !*(_DWORD *)&v56[4] )
          goto LABEL_187;
        v51 = -(int)v41 & 0xFFF;
        if ( v51 > v35 )
          v51 = (unsigned int)v35;
        v36 = (char *)v39 + v51;
        Buffer = v36;
        v37 = v51 + v40;
        *(_QWORD *)&v76 = v37;
        v35 -= v51;
        v68 = v35;
        v63 = v35;
        if ( !v35 )
        {
LABEL_187:
          v27 = *(_DWORD *)&v56[4];
          goto LABEL_188;
        }
        goto LABEL_149;
      }
      v58 = 0;
      v42 = *v39;
      LODWORD(v63) = *v39;
      v43 = v39[14];
      if ( (v43 & DWORD2(v76)) != 0 && (!HIDWORD(v76) || v43 < 0) && *((_WORD *)v39 + 2) == 3 )
        break;
LABEL_182:
      v40 += v42;
      *(_QWORD *)&v76 = v40;
      v39 = (unsigned int *)((char *)v39 + v42);
      Buffer = v39;
      v35 -= v42;
      v68 = v35;
      v63 = v35;
    }
    if ( WORD5(v78) >= 3u )
    {
      v49 = 76;
      v58 = 76;
      v50 = v56[1];
      if ( !v56[1] )
      {
        v49 = *((unsigned __int16 *)v39 + 36) + 76;
        v58 = v49;
      }
      v45 = (v49 + 7) & 0xFFFFFFF8;
      v58 = v45;
      if ( v45 > *(_DWORD *)&v56[4] )
      {
LABEL_170:
        v27 = 0;
        *(_DWORD *)&v56[4] = 0;
LABEL_188:
        CcUnpinData(Bcb);
        Bcb = 0;
        v29 = v76;
        goto LABEL_144;
      }
      *(_OWORD *)v28 = *(_OWORD *)v39;
      *((_OWORD *)v28 + 1) = *((_OWORD *)v39 + 1);
      *((_OWORD *)v28 + 2) = *((_OWORD *)v39 + 2);
      *((_OWORD *)v28 + 3) = *((_OWORD *)v39 + 3);
      *((_QWORD *)v28 + 8) = *((_QWORD *)v39 + 8);
      *(_DWORD *)v28 = v45;
      v28[37] = 76;
      if ( v50 )
      {
        v28[36] = 0;
        goto LABEL_181;
      }
      v28[36] = *((_WORD *)Buffer + 36);
      v48 = v28 + 38;
    }
    else
    {
      v44 = 60;
      v58 = 60;
      if ( !v56[1] )
      {
        v44 = *((unsigned __int16 *)v39 + 36) + 60;
        v58 = v44;
      }
      v45 = (v44 + 7) & 0xFFFFFFF8;
      v58 = v45;
      if ( v45 > *(_DWORD *)&v56[4] )
        goto LABEL_170;
      *(_DWORD *)v28 = v45;
      *((_DWORD *)v28 + 1) = 2;
      *((_QWORD *)v28 + 1) = RefsPackFileId((const struct _REFS_FILE_REFERENCE *)((char *)Buffer + 8));
      *((_QWORD *)v28 + 2) = RefsPackFileId((const struct _REFS_FILE_REFERENCE *)((char *)Buffer + 24));
      v46 = (char *)Buffer;
      *(_OWORD *)(v28 + 12) = *(_OWORD *)((char *)Buffer + 40);
      *(_OWORD *)(v28 + 20) = *(_OWORD *)(v46 + 56);
      v28[29] = 60;
      if ( v47 )
      {
        v28[28] = 0;
LABEL_181:
        v28 = (_WORD *)((char *)v28 + v45);
        v73 = v28;
        *(_DWORD *)&v56[4] -= v45;
        v62 += v45;
        v39 = (unsigned int *)Buffer;
        v40 = v76;
        v41 = v69;
        v35 = v68;
        goto LABEL_182;
      }
      v28[28] = *((_WORD *)Buffer + 36);
      v48 = v28 + 30;
    }
    memmove(v48, (char *)Buffer + 76, *((unsigned __int16 *)Buffer + 36));
    v42 = v63;
    goto LABEL_181;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v10 = -1073741592;
  }
  else
  {
    v10 = -1073741592;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids, 3221225704LL);
  }
  if ( !(_BYTE)RefsStatusDebugEnabled )
    goto LABEL_214;
  v23 = 1256;
LABEL_213:
  RefsStatusDebug(v10, 0, "UsnSup.c", v23);
LABEL_214:
  v38 = v54;
LABEL_225:
  if ( Bcb )
    CcUnpinData(Bcb);
  if ( v38 )
  {
    v52 = *((_DWORD *)v7 + 1);
    if ( (v52 & 0x2000) != 0 )
    {
      *((_DWORD *)v7 + 1) = v52 & 0xFFFFCFFF;
      ExReleaseFastResource((char *)v19 + 1208, v75);
    }
  }
  if ( v55 )
    RefsReleaseVcb(v7, v19);
  *((_QWORD *)v7 + 1) &= ~v72;
  v53 = 0;
  if ( v10 != 259 )
    v53 = v6;
  if ( v6 != *((PIRP *)v7 + 9) )
    v7 = 0;
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v7, v53, v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1402e81e0  mov     r11, rsp
0x1402e81e3  push    rbx
0x1402e81e4  push    rsi
0x1402e81e5  push    rdi
0x1402e81e6  push    r12
0x1402e81e8  push    r13
0x1402e81ea  push    r14
0x1402e81ec  push    r15
0x1402e81ee  sub     rsp, 170h
0x1402e81f5  mov     rax, cs:__security_cookie
0x1402e81fc  xor     rax, rsp
0x1402e81ff  mov     [rsp+1A8h+var_48], rax
0x1402e8207  mov     bl, r9b
0x1402e820a  mov     [rsp+1A8h+var_158+1], bl
0x1402e820e  mov     r15b, r8b
0x1402e8211  mov     [rsp+1A8h+var_150], r8b
0x1402e8216  mov     r13, rdx
0x1402e8219  mov     [rsp+1A8h+Irp], rdx
0x1402e821e  mov     rsi, rcx
0x1402e8221  mov     [rsp+1A8h+var_F0], rcx
0x1402e8229  xor     r12d, r12d
0x1402e822c  mov     [rsp+1A8h+var_148], r12
0x1402e8231  mov     [r11-120h], r12
0x1402e8238  xorps   xmm0, xmm0
0x1402e823b  movups  xmmword ptr [r11-78h], xmm0
0x1402e8240  movups  xmmword ptr [r11-68h], xmm0
0x1402e8245  movups  xmmword ptr [r11-58h], xmm0
0x1402e824a  mov     [r11-118h], r12
0x1402e8251  mov     [r11-0F8h], r12
0x1402e8258  mov     [r11-110h], r12
0x1402e825f  xor     edx, edx; Val
0x1402e8261  lea     r8d, [r12+48h]; Size
0x1402e8266  lea     rcx, [r11-0C8h]; void *
0x1402e826d  call    memset
0x1402e8272  lea     rcx, [rsp+1A8h+var_C8]
0x1402e827a  call    cs:__imp_ExInitializeFastOwnerEntry
0x1402e8281  nop     dword ptr [rax+rax+00h]
0x1402e8286  mov     r14, [r13+0B8h]
0x1402e828d  mov     byte ptr [rsp+1A8h+var_178], 1
0x1402e8292  lea     rax, [rsp+1A8h+var_110]
0x1402e829a  mov     [rsp+1A8h+Buffer], rax
0x1402e829f  lea     rax, [rsp+1A8h+FileOffset]
0x1402e82a7  mov     [rsp+1A8h+Bcb], rax
0x1402e82ac  lea     r9, [rsp+1A8h+var_E8]
0x1402e82b4  lea     r8, [rsp+1A8h+var_118]
0x1402e82bc  mov     rdx, [r14+30h]
0x1402e82c0  mov     rcx, rsi
0x1402e82c3  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x1402e82c8  test    bl, bl
0x1402e82ca  jnz     loc_1402E837D
0x1402e82d0  mov     rax, [rsp+1A8h+var_110]
0x1402e82d8  test    rax, rax
0x1402e82db  jz      short loc_1402E8303
0x1402e82dd  movzx   eax, word ptr [rax+58h]
0x1402e82e1  bt      ax, 9
0x1402e82e6  jb      loc_1402E837D
0x1402e82ec  cmp     [r13+40h], r12b
0x1402e82f0  jnz     short loc_1402E8303
0x1402e82f2  lea     edi, [r12+4]
0x1402e82f7  cmp     [r14+1], dil
0x1402e82fb  jz      loc_1402E8382
0x1402e8301  jmp     short loc_1402E8308
0x1402e8303  mov     edi, 4
0x1402e8308  mov     ebx, 0C0000022h
0x1402e830d  mov     r8d, ebx; Status
0x1402e8310  mov     rdx, r13; Irp
0x1402e8313  mov     rcx, rsi; struct _IRP_CONTEXT *
0x1402e8316  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402e831b  lea     rax, WPP_GLOBAL_Control
0x1402e8322  mov     rcx, cs:WPP_GLOBAL_Control
0x1402e8329  cmp     rcx, rax
0x1402e832c  jz      short loc_1402E8355
0x1402e832e  test    dword ptr [rcx+2Ch], 100h
0x1402e8335  jz      short loc_1402E8355
0x1402e8337  cmp     [rcx+29h], dil
0x1402e833b  jb      short loc_1402E8355
0x1402e833d  mov     edx, 11h
0x1402e8342  mov     r9d, ebx
0x1402e8345  lea     r8, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids
0x1402e834c  mov     rcx, [rcx+18h]
0x1402e8350  call    WPP_SF_d
0x1402e8355  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402e835b  test    cl, cl
0x1402e835d  jz      short loc_1402E8375
0x1402e835f  mov     r9d, 47Ch; unsigned int
0x1402e8365  lea     r8, aUsnsupC; "UsnSup.c"
0x1402e836c  xor     edx, edx; struct _IRP_CONTEXT *
0x1402e836e  mov     ecx, ebx; Status
0x1402e8370  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402e8375  mov     eax, ebx
0x1402e8377  jmp     loc_1402E9429
0x1402e837d  mov     edi, 4
0x1402e8382  mov     al, r12b
0x1402e8385  mov     [rsp+1A8h+var_164], eax
0x1402e8389  mov     [rsp+1A8h+var_160], al
0x1402e838d  mov     [rsp+1A8h+var_168], r12b
0x1402e8392  mov     [rsp+1A8h+var_15F], r12b
0x1402e8397  mov     dl, 1
0x1402e8399  mov     [rsp+1A8h+var_138], edx
0x1402e839d  test    r15b, r15b
0x1402e83a0  jz      short loc_1402E83B3
0x1402e83a2  mov     al, [rsi+8]
0x1402e83a5  and     al, dl
0x1402e83a7  neg     al
0x1402e83a9  sbb     al, al
0x1402e83ab  and     al, dl
0x1402e83ad  mov     dl, al
0x1402e83af  mov     [rsp+1A8h+var_138], edx
0x1402e83b3  mov     rax, [rsi+8]
0x1402e83b7  mov     rcx, rax
0x1402e83ba  not     rcx
0x1402e83bd  and     ecx, 1
0x1402e83c0  mov     [rsp+1A8h+var_E8], rcx
0x1402e83c8  mov     [rsp+1A8h+var_D8], rcx
0x1402e83d0  or      rax, 1
0x1402e83d4  mov     [rsi+8], rax
0x1402e83d8  mov     rdx, r14; struct _IO_STACK_LOCATION *
0x1402e83db  mov     rcx, r13; struct _IRP *
0x1402e83de  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x1402e83e3  mov     r12b, al
0x1402e83e6  mov     [rsp+1A8h+var_168], 1
0x1402e83eb  mov     r9d, [r14+8]; unsigned int
0x1402e83ef  mov     r8d, 1; enum _LOCK_OPERATION
0x1402e83f5  mov     rdx, r13; struct _IRP *
0x1402e83f8  call    ?RefsLockUserBuffer@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@W4_LOCK_OPERATION@@K@Z; RefsLockUserBuffer(_IRP_CONTEXT *,_IRP *,_LOCK_OPERATION,ulong)
0x1402e83fd  mov     ebx, eax
0x1402e83ff  mov     [rsp+1A8h+var_15C], eax
0x1402e8403  test    eax, eax
0x1402e8405  jns     short loc_1402E846C
0x1402e8407  lea     rax, WPP_GLOBAL_Control
0x1402e840e  mov     rcx, cs:WPP_GLOBAL_Control
0x1402e8415  cmp     rcx, rax
0x1402e8418  jz      short loc_1402E8441
0x1402e841a  test    dword ptr [rcx+2Ch], 100h
0x1402e8421  jz      short loc_1402E8441
0x1402e8423  cmp     [rcx+29h], dil
0x1402e8427  jb      short loc_1402E8441
0x1402e8429  mov     edx, 12h
0x1402e842e  mov     r9d, ebx
0x1402e8431  lea     r8, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids
0x1402e8438  mov     rcx, [rcx+18h]
0x1402e843c  call    WPP_SF_d
0x1402e8441  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402e8447  test    al, al
0x1402e8449  jz      short loc_1402E8462
0x1402e844b  mov     r9d, 4A3h; unsigned int
0x1402e8451  lea     r8, aUsnsupC; "UsnSup.c"
0x1402e8458  mov     rdx, rsi; struct _IRP_CONTEXT *
0x1402e845b  mov     ecx, ebx; Status
0x1402e845d  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402e8462  mov     edx, ebx; int
0x1402e8464  mov     rcx, rsi; struct _IRP_CONTEXT *
0x1402e8467  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x1402e846c  mov     rcx, r13; struct _IRP *
0x1402e846f  call    ?RefsMapUserBuffer@@YAPEAXPEAU_IRP@@K@Z; RefsMapUserBuffer(_IRP *,ulong)
0x1402e8474  mov     r9, rax
0x1402e8477  mov     [rsp+1A8h+var_110], rax
0x1402e847f  cmp     byte ptr [r13+40h], 0
0x1402e8484  jz      short loc_1402E84C9
0x1402e8486  test    r15b, r15b
0x1402e8489  jz      short loc_1402E84AA
0x1402e848b  mov     edx, [r14+10h]; Length
0x1402e848f  mov     r8d, edi; Alignment
0x1402e8492  mov     rcx, [r14+20h]; Address
0x1402e8496  call    cs:__imp_ProbeForRead
0x1402e849d  nop     dword ptr [rax+rax+00h]
0x1402e84a2  mov     r9, [rsp+1A8h+var_110]
0x1402e84aa  cmp     qword ptr [r13+8], 0
0x1402e84af  jnz     short loc_1402E84F6
0x1402e84b1  mov     edx, [r14+8]; Length
0x1402e84b5  mov     r8d, edi; Alignment
0x1402e84b8  mov     rcx, r9; Address
0x1402e84bb  call    cs:__imp_ProbeForWrite
0x1402e84c2  nop     dword ptr [rax+rax+00h]
0x1402e84c7  jmp     short loc_1402E84F6
0x1402e84c9  mov     rcx, [r14+20h]
0x1402e84cd  lea     rax, [rcx+3]
0x1402e84d1  and     rax, 0FFFFFFFFFFFFFFFCh
0x1402e84d5  cmp     rcx, rax
0x1402e84d8  jnz     loc_1402E91F5
0x1402e84de  cmp     qword ptr [r13+8], 0
0x1402e84e3  jnz     short loc_1402E84F6
0x1402e84e5  lea     rax, [r9+3]
0x1402e84e9  and     rax, 0FFFFFFFFFFFFFFFCh
0x1402e84ed  cmp     r9, rax
0x1402e84f0  jnz     loc_1402E91F5
0x1402e84f6  mov     [rsp+1A8h+var_168], 0
0x1402e84fb  test    r15b, r15b
0x1402e84fe  mov     r15, [rsp+1A8h+var_118]
0x1402e8506  jz      short loc_1402E851A
0x1402e8508  mov     r8b, 1; unsigned __int8
0x1402e850b  mov     rdx, r15; struct _VCB *
0x1402e850e  mov     rcx, rsi; struct _IRP_CONTEXT *
0x1402e8511  call    ?RefsAcquireSharedVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireSharedVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x1402e8516  mov     [rsp+1A8h+var_15F], al
0x1402e851a  lea     rcx, [r15+4B8h]
0x1402e8521  mov     r8b, 1
0x1402e8524  lea     rdx, [rsp+1A8h+var_C8]
0x1402e852c  call    cs:__imp_ExAcquireFastResourceShared
0x1402e8533  nop     dword ptr [rax+rax+00h]
0x1402e8538  bts     dword ptr [rsi+4], 0Dh
0x1402e853d  mov     al, 1
0x1402e853f  mov     [rsp+1A8h+var_164], eax
0x1402e8543  mov     [rsp+1A8h+var_160], al
0x1402e8547  mov     ecx, [r15+18h]
0x1402e854b  mov     eax, ecx
0x1402e854d  and     eax, 100000h
0x1402e8552  jz      short loc_1402E85C9
0x1402e8554  lea     rax, WPP_GLOBAL_Control
0x1402e855b  mov     rcx, cs:WPP_GLOBAL_Control
0x1402e8562  cmp     rcx, rax
0x1402e8565  jz      short loc_1402E8596
0x1402e8567  mov     eax, [rcx+2Ch]
0x1402e856a  bt      eax, 8
0x1402e856e  jnb     short loc_1402E8596
0x1402e8570  cmp     [rcx+29h], dil
0x1402e8574  jb      short loc_1402E8596
0x1402e8576  mov     edx, 14h
0x1402e857b  mov     r13d, 0C00002B7h
0x1402e8581  mov     r9d, r13d
0x1402e8584  lea     r8, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids
0x1402e858b  mov     rcx, [rcx+18h]
0x1402e858f  call    WPP_SF_d
0x1402e8594  jmp     short loc_1402E859C
0x1402e8596  mov     r13d, 0C00002B7h
0x1402e859c  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402e85a2  test    al, al
0x1402e85a4  jz      short loc_1402E85BD
0x1402e85a6  mov     r9d, 4D6h; unsigned int
0x1402e85ac  lea     r8, aUsnsupC; "UsnSup.c"
0x1402e85b3  xor     edx, edx; struct _IRP_CONTEXT *
0x1402e85b5  mov     ecx, r13d; Status
0x1402e85b8  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402e85bd  mov     ebx, r13d
0x1402e85c0  mov     [rsp+1A8h+var_15C], ebx
0x1402e85c4  jmp     loc_1402E9269
0x1402e85c9  cmp     qword ptr [r15+28h], 0
0x1402e85ce  jz      loc_1402E9184
0x1402e85d4  and     ecx, 80000h
0x1402e85da  jz      loc_1402E9184
0x1402e85e0  mov     eax, [r14+10h]
0x1402e85e4  cmp     eax, 28h ; '('
0x1402e85e7  jnb     short loc_1402E8648
0x1402e85e9  lea     rax, WPP_GLOBAL_Control
0x1402e85f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1402e85f7  cmp     rcx, rax
0x1402e85fa  jz      short loc_1402E862A
0x1402e85fc  mov     eax, [rcx+2Ch]
0x1402e85ff  bt      eax, 8
0x1402e8603  jnb     short loc_1402E862A
0x1402e8605  cmp     [rcx+29h], dil
0x1402e8609  jb      short loc_1402E862A
0x1402e860b  mov     edx, 16h
0x1402e8610  mov     ebx, 0C00000E8h
0x1402e8615  mov     r9d, ebx
0x1402e8618  lea     r8, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids
0x1402e861f  mov     rcx, [rcx+18h]
0x1402e8623  call    WPP_SF_d
0x1402e8628  jmp     short loc_1402E862F
0x1402e862a  mov     ebx, 0C00000E8h
0x1402e862f  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402e8635  test    al, al
0x1402e8637  jz      loc_1402E91EA
0x1402e863d  mov     r9d, 4E8h
0x1402e8643  jmp     loc_1402E91DA
0x1402e8648  mov     r8d, 30h ; '0'
0x1402e864e  cmp     eax, r8d
0x1402e8651  jz      short loc_1402E8664
0x1402e8653  mov     [rsp+1A8h+var_50], 20002h
0x1402e865e  mov     r8d, 28h ; '('; Size
0x1402e8664  mov     [rsp+1A8h+var_168], 1
0x1402e8669  mov     rdx, [r14+20h]; Src
0x1402e866d  lea     rcx, [rsp+1A8h+var_78]; void *
0x1402e8675  test    r12b, r12b
0x1402e8678  jz      short loc_1402E8681
0x1402e867a  call    RtlCopyFromUser
0x1402e867f  jmp     short loc_1402E8686
0x1402e8681  call    RtlCopyVolatileMemory
0x1402e8686  nop
0x1402e8687  mov     [rsp+1A8h+var_168], 0
0x1402e868c  mov     rax, [rsp+1A8h+var_58]
0x1402e8694  cmp     rax, [r15+388h]
0x1402e869b  jz      short loc_1402E86FC
0x1402e869d  lea     rax, WPP_GLOBAL_Control
0x1402e86a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1402e86ab  cmp     rcx, rax
0x1402e86ae  jz      short loc_1402E86DE
0x1402e86b0  mov     eax, [rcx+2Ch]
0x1402e86b3  bt      eax, 8
0x1402e86b7  jnb     short loc_1402E86DE
0x1402e86b9  cmp     [rcx+29h], dil
0x1402e86bd  jb      short loc_1402E86DE
0x1402e86bf  mov     edx, 17h
0x1402e86c4  mov     ebx, 0C000000Dh
0x1402e86c9  mov     r9d, ebx
0x1402e86cc  lea     r8, WPP_8528fa72243c3049f9bfe819fea9b2e0_Traceguids
0x1402e86d3  mov     rcx, [rcx+18h]
0x1402e86d7  call    WPP_SF_d
0x1402e86dc  jmp     short loc_1402E86E3
0x1402e86de  mov     ebx, 0C000000Dh
  ... truncated ...
```
