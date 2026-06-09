# RefsScrubHandleInternal(_IRP_CONTEXT *,_IRP *,_SmsCancelScrub *,_SCB *,_TYPE_OF_OPEN)

- ea: `0x1402c072c`
- end: `0x1402c1d47`
- name: `?RefsScrubHandleInternal@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_SmsCancelScrub@@PEAU_SCB@@W4_TYPE_OF_OPEN@@@Z`
- size: `5659`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1402c0254`

## callees

- `0x1400298a0`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400d0fd8`
- `0x1400ebde0`
- `0x1400f7424`
- `0x1400f84c0`
- `0x1400f851c`
- `0x1400f873c`
- `0x1400f87a8`
- `0x140119878`
- `0x14011ac24`
- `0x14011ac78`
- `0x14011aca8`
- `0x14011ad6c`
- `0x14011ad7c`
- `0x14011adcc`
- `0x14011adf4`
- `0x1401f3fc0`
- `0x1401f4100`
- `0x1401f4400`
- `0x14029d5e8`
- `0x1402a0310`
- `0x1402a03fc`
- `0x1402c072c`
- `0x140302e10`

## import_xrefs

- `ntoskrnl!PsIsThreadTerminating` at `0x1402c0fca`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c1095`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c11a2`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c1267`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c135b`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c141f`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c14c1`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c1595`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c16c4`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c0fca`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c1095`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c11a2`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c1267`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c135b`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c141f`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c14c1`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c1595`
- `ntoskrnl!PsIsThreadTerminating` at `0x1402c16c4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402c1733`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1402c1733`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402c1742`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1402c1742`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402c176d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402c176d`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402c1779`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1402c1779`

## pseudocode

```c
void __fastcall RefsScrubHandleInternal(
        struct CmsTransactionContext **a1,
        struct _IRP *a2,
        __int64 a3,
        __int16 *a4,
        unsigned __int8 a5)
{
  NTSTATUS v8; // r14d
  struct _IO_STACK_LOCATION *v9; // r8
  unsigned int Options; // edx
  unsigned int v11; // r9d
  struct _IRP *MasterIrp; // r15
  _DWORD *v13; // rbx
  _DWORD *v14; // rsi
  int v15; // ecx
  unsigned int v16; // eax
  __int64 v17; // rax
  struct _LIST_ENTRY *Blink; // rdx
  __int64 v19; // rax
  __int64 v20; // r8
  int MdlAddress; // eax
  unsigned int v22; // r8d
  struct _MDL **v23; // r9
  ULONG v24; // ecx
  _DWORD *v25; // rcx
  __int64 v26; // rdx
  unsigned int Length; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  struct CmsTransactionContext **v32; // rbx
  int v33; // r9d
  __int64 v34; // rcx
  unsigned int v35; // ecx
  _QWORD *v36; // rdi
  __int64 v37; // rcx
  __int64 v38; // rcx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rcx
  struct CmsTransactionContext **v46; // rbx
  __int64 v47; // rcx
  __int64 v48; // rcx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  int v56; // r9d
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // r8
  NTSTATUS v60; // r9d
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  struct _FAST_MUTEX *v64; // rbx
  __int64 v65; // rbx
  unsigned __int64 v66; // rdx
  __int16 *v67; // rbx
  CmsStream *v68; // r8
  struct _LIST_ENTRY *Flink; // rbx
  struct _IRP *v70; // r13
  unsigned __int16 *v71; // rdx
  __int64 Information_low; // rbx
  size_t v73; // rdi
  struct _VCB *v74; // rcx
  __int128 v75; // xmm0
  __int128 v76; // xmm1
  struct _IRP *v77; // r13
  unsigned __int16 *v78; // rdx
  size_t v79; // rbx
  void **v80; // [rsp+30h] [rbp-288h]
  __int64 v81; // [rsp+40h] [rbp-278h]
  char v83; // [rsp+50h] [rbp-268h]
  unsigned int v84; // [rsp+54h] [rbp-264h] BYREF
  __int64 v85; // [rsp+58h] [rbp-260h]
  __int16 *v86; // [rsp+60h] [rbp-258h]
  unsigned __int64 v87; // [rsp+68h] [rbp-250h]
  void *v88; // [rsp+70h] [rbp-248h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+78h] [rbp-240h]
  struct _IRP *v90; // [rsp+80h] [rbp-238h]
  __int64 v91; // [rsp+88h] [rbp-230h]
  __int64 v92; // [rsp+90h] [rbp-228h]
  __int128 v93; // [rsp+A8h] [rbp-210h]
  _OWORD v94[11]; // [rsp+B8h] [rbp-200h] BYREF
  __int128 v95; // [rsp+178h] [rbp-140h]
  _OWORD v96[11]; // [rsp+188h] [rbp-130h] BYREF
  __int128 v97; // [rsp+238h] [rbp-80h] BYREF
  __int128 v98; // [rsp+248h] [rbp-70h]
  __int128 v99; // [rsp+258h] [rbp-60h]
  __int64 v100; // [rsp+268h] [rbp-50h]

  v86 = a4;
  v90 = a2;
  v8 = 0;
  v88 = 0;
  v84 = 0x100000;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v9 = CurrentStackLocation;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v100 = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options < 0xC0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 456, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225485LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v11 = 16535;
LABEL_77:
      RefsStatusDebug(-1073741811, 0, "FsCtrl.c", v11);
      return;
    }
    return;
  }
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  if ( *(_DWORD *)&MasterIrp->Type == 1232 )
  {
    v85 = *((_QWORD *)a4 + 18);
    v13 = &MasterIrp->Size + 1;
    if ( *(_DWORD *)(v85 + 392) < 2u && (*v13 & 8) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          458,
          &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
          3221226617LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073740679, 0, "FsCtrl.c", 0x40B1u);
      return;
    }
    v14 = &MasterIrp->Tail.CompletionKey + 9;
    v15 = *v13 & 1;
    if ( v15 )
    {
      v16 = *((_DWORD *)&MasterIrp->Tail.CompletionKey + 21);
      if ( v16 > 0x280 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            459,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221225485LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v11 = 16573;
          goto LABEL_77;
        }
        return;
      }
      if ( Options < v16 + 296 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            460,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221225485LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v11 = 16581;
          goto LABEL_77;
        }
        return;
      }
    }
    if ( CurrentStackLocation->Parameters.Read.Length < 0x4D0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          461,
          &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
          3221225507LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741789, 0, "FsCtrl.c", 0x40D0u);
      return;
    }
    v91 = *((_QWORD *)a4 + 17);
    if ( v15 )
    {
      if ( *v14 != 2
        || *((_BYTE *)&MasterIrp->Tail.CompletionKey + 76) >= 0x16u
        || *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) >= 5u
        || *((_BYTE *)&MasterIrp->Tail.CompletionKey + 78) >= 0xAu
        || (v17 = *((unsigned int *)&MasterIrp->Tail.CompletionKey + 21), (unsigned int)v17 > 0x4D0)
        || (_DWORD *)((char *)v14 + v17 + 104) > (_DWORD *)&MasterIrp[6].Tail.CompletionKey + 14 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            462,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221225485LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v11 = 16610;
          goto LABEL_77;
        }
        return;
      }
    }
    else
    {
      *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 0;
      *((_BYTE *)&MasterIrp->Tail.CompletionKey + 78) = 9;
      MsInitializeScrubKey(&MasterIrp->Tail.CompletionKey + 9);
      memset(&MasterIrp[1].MdlAddress, 0, 0x50u);
    }
    Blink = MasterIrp->ThreadListEntry.Blink;
    if ( Blink )
    {
      if ( a5 == 4 || (unsigned __int16)(*a4 - 2051) <= 1u )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, Blink, v9, a5, *v86);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            464,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221225659LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741637, 0, "FsCtrl.c", 0x4101u);
        return;
      }
      v19 = *((_QWORD *)a4 + 18);
      v20 = *(unsigned int *)(v19 + 272);
      if ( (((_DWORD)v20 - 1) & (__int64)MasterIrp->ThreadListEntry.Flink) != 0
        || Blink != (struct _LIST_ENTRY *)-1LL && ((unsigned int)Blink & ((_DWORD)v20 - 1)) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_iiD(
            WPP_GLOBAL_Control->AttachedDevice,
            Blink,
            v20,
            MasterIrp->ThreadListEntry.Flink,
            Blink,
            *(_DWORD *)(v19 + 272));
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            466,
            &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
            3221225485LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v11 = 16659;
          goto LABEL_77;
        }
        return;
      }
    }
    v87 = 0xFFFFFFFF00000000uLL;
    MasterIrp[4].CancelRoutine = (PDRIVER_CANCEL)MasterIrp->ThreadListEntry.Flink;
    MasterIrp[4].UserBuffer = MasterIrp->ThreadListEntry.Blink;
    *v14 = 2;
    MdlAddress = (int)MasterIrp->MdlAddress;
    *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) = MdlAddress;
    if ( !MdlAddress )
    {
      MdlAddress = 0x7FFFFFFF;
      *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) = 0x7FFFFFFF;
    }
    if ( MdlAddress < 2 )
      *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) = 2;
    memset(v94, 0, sizeof(v94));
    v23 = 0;
    LODWORD(v93) = 0;
    *((_QWORD *)&v93 + 1) = 0;
    *(_DWORD *)((char *)&v94[3] + 2) = 0;
    WORD3(v94[3]) = 0;
    MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry = 0;
    *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 1) = v93;
    *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 2) = v94[0];
    *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 3) = v94[1];
    *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 4) = v94[2];
    *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 5) = v94[3];
    *(_OWORD *)&MasterIrp[5].MdlAddress = v94[4];
    *(_OWORD *)&MasterIrp[5].AssociatedIrp.MasterIrp = v94[5];
    *(_OWORD *)&MasterIrp[5].ThreadListEntry.Blink = v94[6];
    *(_OWORD *)&MasterIrp[5].IoStatus.Information = v94[7];
    *(_OWORD *)&MasterIrp[5].UserIosb = v94[8];
    *(_OWORD *)&MasterIrp[5].Overlay.AsynchronousParameters.UserApcRoutine = v94[9];
    *(_OWORD *)&MasterIrp[5].CancelRoutine = v94[10];
    MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = (struct _LIST_ENTRY *)&MasterIrp[1].Overlay;
    v24 = *((_DWORD *)&MasterIrp->Tail.CompletionKey + 21);
    LODWORD(MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) = v24;
    WORD2(MasterIrp[4].Tail.CompletionKey) = MasterIrp[1].Type;
    MasterIrp[4].Tail.Overlay.DriverContext[3] = &MasterIrp[1].Overlay;
    MasterIrp[4].Tail.Overlay.DeviceQueueEntry.SortKey = v24;
    v25 = &MasterIrp[4].Tail.CompletionKey + 4;
    v26 = 1;
    if ( (*v13 & 2) != 0 )
      *v25 |= 1u;
    if ( (*v13 & 4) != 0 )
    {
      v25 = &MasterIrp[4].Tail.CompletionKey + 4;
      *((_DWORD *)&MasterIrp[4].Tail.CompletionKey + 8) |= 4u;
    }
    if ( (*v13 & 8) != 0 )
      *v25 |= 8u;
    if ( (*v13 & 0x40) != 0 )
      *v25 |= 0x10u;
    MasterIrp[5].MdlAddress = (PMDL)&MasterIrp[5].Tail;
    LOWORD(MasterIrp[5].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) = 24;
    WORD1(MasterIrp[5].MdlAddress->Next) = 0;
    WORD2(MasterIrp[5].MdlAddress->Next) = 0;
    HIWORD(MasterIrp[5].MdlAddress->Next) = 4;
    Length = CurrentStackLocation->Parameters.Read.Length;
    if ( Length > 0x4D0 )
    {
      v28 = Length - 1232;
      if ( v28 >= 0x4000 )
        LOWORD(v28) = 0x4000;
      HIWORD(MasterIrp[5].MdlAddress->Next) += (unsigned __int16)v28 >> 4;
    }
    *(_QWORD *)&MasterIrp[5].Type = &v97;
    v97 = 0;
    v98 = 0;
    v99 = 0;
    v100 = 0;
    if ( a5 == 4 )
    {
      BYTE4(v81) = 0;
      v29 = *((unsigned __int8 *)&MasterIrp->Tail.CompletionKey + 76);
      if ( v29 <= 0xB )
      {
        if ( v29 != 11 )
        {
          if ( v29 > 5 )
          {
            v35 = v29 - 6;
            if ( v35 )
            {
              v30 = v35 - 1;
              if ( v30 )
              {
LABEL_113:
                v31 = v30 - 1;
                if ( v31 && v31 - 1 >= 2 )
                  goto LABEL_115;
              }
            }
          }
          else if ( v29 != 5 )
          {
            if ( !*((_BYTE *)&MasterIrp->Tail.CompletionKey + 76) || (v30 = v29 - 1) == 0 )
            {
              v32 = a1;
              if ( (*(_DWORD *)(&MasterIrp[4].Tail.CompletionKey + 4) & 1) == 0 )
                v8 = RefsScrubBootSector(
                       (struct _IRP_CONTEXT *)a1,
                       (struct _SmsScrubContext *)(&MasterIrp->Tail.CompletionKey + 9));
              *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 2;
              MsInitializeScrubKey(&MasterIrp->Tail.CompletionKey + 9);
              if ( v8 < 0 )
                goto LABEL_115;
              if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= v33
                || **(_BYTE **)a3 != (_BYTE)v33
                || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
                || PsIsThreadTerminating(KeGetCurrentThread())
                || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
                || (unsigned __int8)MsScrubContextParityExtentDataFull(&MasterIrp->Tail.CompletionKey + 9) )
              {
                goto LABEL_257;
              }
              *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 2;
              MsInitializeScrubKey(v34);
              goto LABEL_130;
            }
            goto LABEL_113;
          }
        }
LABEL_129:
        v32 = a1;
LABEL_130:
        v36 = (_QWORD *)v85;
        v8 = MsScrubVolumeMetaData(v32[3], (struct _SmsCancelScrub *)a3, *(CmsVolume **)(v85 + 112));
        if ( v8 < 0 )
          goto LABEL_115;
        RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)v32);
        RefsBindMinstoreTransaction((struct _IRP_CONTEXT *)v32);
        if ( *((int *)&MasterIrp->Tail.CompletionKey + 20) <= 0
          || **(_BYTE **)a3
          || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
          || PsIsThreadTerminating(KeGetCurrentThread())
          || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
          || (unsigned __int8)MsScrubContextParityExtentDataFull(v37) )
        {
          goto LABEL_257;
        }
        *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 16;
        MsInitializeScrubKey(v38);
        goto LABEL_146;
      }
      if ( v29 > 0x11 )
      {
        v49 = v29 - 18;
        if ( !v49 )
        {
          v46 = a1;
          v36 = (_QWORD *)v85;
LABEL_176:
          if ( (struct _MDL **)v36[22] != v23 )
          {
            MsScrubSetTableIndex(18, &MasterIrp->Tail.CompletionKey + 9);
            v8 = MsScrubTable(v46[3], a3, v36[22], &MasterIrp->Tail.CompletionKey + 9);
            MsScrubClearTableIndex(&MasterIrp->Tail.CompletionKey + 9);
            LODWORD(v23) = 0;
          }
          if ( v8 < 0 )
            goto LABEL_115;
          if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= (int)v23
            || **(_BYTE **)a3 != (_BYTE)v23
            || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread()) )
          {
            v8 = -2147483643;
            goto LABEL_115;
          }
          if ( (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
            || (unsigned __int8)MsScrubContextParityExtentDataFull(v52) )
          {
            goto LABEL_257;
          }
          *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 19;
          MsInitializeScrubKey(v53);
          goto LABEL_186;
        }
        v50 = v49 - 1;
        if ( !v50 )
        {
          v36 = (_QWORD *)v85;
LABEL_186:
          if ( (struct _MDL **)v36[23] == v23 )
          {
            v32 = a1;
          }
          else
          {
            MsScrubSetTableIndex(19, &MasterIrp->Tail.CompletionKey + 9);
            v32 = a1;
            v8 = MsScrubTable(a1[3], a3, v36[23], &MasterIrp->Tail.CompletionKey + 9);
            MsScrubClearTableIndex(&MasterIrp->Tail.CompletionKey + 9);
            LODWORD(v23) = 0;
          }
          if ( v8 < 0 )
            goto LABEL_115;
          if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= (int)v23
            || **(_BYTE **)a3 != (_BYTE)v23
            || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
            || (unsigned __int8)MsScrubContextParityExtentDataFull(v54) )
          {
            goto LABEL_257;
          }
          *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 20;
          MsInitializeScrubKey(v55);
          goto LABEL_197;
        }
        v51 = v50 - 1;
        v32 = a1;
        if ( !v51 )
        {
LABEL_197:
          v8 = RefsScrubVerifyBlock(
                 (struct _IRP_CONTEXT *)v32,
                 v90,
                 (struct _SmsScrubContext *)(&MasterIrp->Tail.CompletionKey + 9));
          *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 21;
          MsInitializeScrubKey(&MasterIrp->Tail.CompletionKey + 9);
          if ( v8 < 0 )
            goto LABEL_115;
          if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= v56
            || **(_BYTE **)a3 != (_BYTE)v56
            || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
            || (unsigned __int8)MsScrubContextParityExtentDataFull(v57) )
          {
            goto LABEL_257;
          }
          *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 21;
          MsInitializeScrubKey(v58);
          goto LABEL_205;
        }
        if ( v51 == 1 )
        {
LABEL_205:
          v22 = v85;
          if ( *(struct _MDL ***)(v85 + 40) != v23 )
          {
            MsScrubSetTableIndex(21, &MasterIrp->Tail.CompletionKey + 9);
            if ( !*((_BYTE *)&MasterIrp->Tail.CompletionKey + 77)
              || *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) == 1 )
            {
              v8 = MsScrubTable(
                     v32[3],
                     a3,
                     *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v59 + 40) + 136LL) + 264LL),
                     &MasterIrp->Tail.CompletionKey + 9);
              if ( v8 < 0 )
              {
LABEL_221:
                MsScrubClearTableIndex(&MasterIrp->Tail.CompletionKey + 9);
                goto LABEL_115;
              }
              if ( *((int *)&MasterIrp->Tail.CompletionKey + 20) <= 0
                || **(_BYTE **)a3
                || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
                || PsIsThreadTerminating(KeGetCurrentThread())
                || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
                || (unsigned __int8)MsScrubContextParityExtentDataFull(v61) )
              {
                v8 = -2147483643;
                goto LABEL_221;
              }
              *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) = 2;
              MsInitializeScrubKey(v62);
            }
            else if ( *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) != 2
                   && *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) != 4 )
            {
              goto LABEL_221;
            }
            v8 = v60;
            goto LABEL_221;
          }
LABEL_115:
          v32 = a1;
        }
      }
      else
      {
        if ( v29 == 17 )
        {
          v36 = (_QWORD *)v85;
LABEL_158:
          if ( (struct _MDL **)v36[13] == v23 )
          {
            v46 = a1;
          }
          else
          {
            MsScrubSetTableIndex(17, &MasterIrp->Tail.CompletionKey + 9);
            v46 = a1;
            v8 = MsScrubTable(a1[3], a3, v36[13], &MasterIrp->Tail.CompletionKey + 9);
            MsScrubClearTableIndex(&MasterIrp->Tail.CompletionKey + 9);
            LODWORD(v23) = 0;
          }
          if ( v8 < 0 )
            goto LABEL_115;
          if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= (int)v23
            || **(_BYTE **)a3 != (_BYTE)v23
            || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
            || (unsigned __int8)MsScrubContextParityExtentDataFull(v47) )
          {
            goto LABEL_257;
          }
          *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 18;
          MsInitializeScrubKey(v48);
          goto LABEL_176;
        }
        v39 = v29 - 12;
        if ( !v39 )
          goto LABEL_129;
        v40 = v39 - 1;
        if ( !v40 )
          goto LABEL_129;
        v41 = v40 - 1;
        if ( !v41 )
          goto LABEL_129;
        v42 = v41 - 1;
        if ( !v42 )
          goto LABEL_129;
        v32 = a1;
        if ( v42 == 1 )
        {
          v36 = (_QWORD *)v85;
LABEL_146:
          v43 = v36[11];
          if ( v43 && *(struct _MDL ***)(v43 + 416) != v23 )
          {
            MsScrubSetTableIndex(16, &MasterIrp->Tail.CompletionKey + 9);
            v8 = MsScrubTable(v32[3], a3, *(_QWORD *)(v36[11] + 416LL), &MasterIrp->Tail.CompletionKey + 9);
            MsScrubClearTableIndex(&MasterIrp->Tail.CompletionKey + 9);
            LODWORD(v23) = 0;
          }
          if ( v8 < 0 )
            goto LABEL_115;
          if ( *((_DWORD *)&MasterIrp->Tail.CompletionKey + 20) <= (int)v23
            || **(_BYTE **)a3 != (_BYTE)v23
            || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
            || (unsigned __int8)MsScrubContextParityExtentDataFull(v44) )
          {
            goto LABEL_257;
          }
          *((_WORD *)&MasterIrp->Tail.CompletionKey + 38) = 17;
          MsInitializeScrubKey(v45);
          goto LABEL_158;
        }
      }
LABEL_256:
      if ( v8 != -2147483643 )
      {
        if ( v8 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              469,
              &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
              (unsigned int)v8);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v8, (struct _IRP_CONTEXT *)v32, "FsCtrl.c", 0x4325u);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)v32, v8, v22);
          __debugbreak();
          return;
        }
        *(_QWORD *)&MasterIrp->Type = 1232;
        LODWORD(MasterIrp->MdlAddress) = 0;
        v77 = v90;
        v90->IoStatus.Information = 192;
        v78 = (unsigned __int16 *)MasterIrp[5].MdlAddress;
        if ( v78[2] )
        {
          v79 = 16LL * v78[2] + 8;
          memmove(&MasterIrp->Tail.CompletionKey + 9, v78, v79);
          WORD1(MasterIrp->IoStatus.Information) = 192;
          *(_DWORD *)(&MasterIrp->Size + 1) |= 0x20000u;
          v77->IoStatus.Information += v79;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              470,
              &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids,
              WORD2(MasterIrp[5].MdlAddress->Next));
          }
        }
        MasterIrp->UserIosb = (PIO_STATUS_BLOCK)(v87 & -(__int64)(BYTE4(v81) != 0));
        RefsScrubConvertMsScrubContextToScrubOutput((struct _SCRUB_DATA_INPUT *)MasterIrp, BYTE4(v81));
        memset(v96, 0, sizeof(v96));
        LODWORD(v95) = 0;
        *((_QWORD *)&v95 + 1) = 0;
        *(_DWORD *)((char *)&v96[3] + 2) = 0;
        WORD3(v96[3]) = 0;
        MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry = 0;
        *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 1) = v95;
        *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 2) = v96[0];
        *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 3) = v96[1];
        *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 4) = v96[2];
        *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 5) = v96[3];
        *(_OWORD *)&MasterIrp[5].MdlAddress = v96[4];
        *(_OWORD *)&MasterIrp[5].AssociatedIrp.MasterIrp = v96[5];
        *(_OWORD *)&MasterIrp[5].ThreadListEntry.Blink = v96[6];
        *(_OWORD *)&MasterIrp[5].IoStatus.Information = v96[7];
        *(_OWORD *)&MasterIrp[5].UserIosb = v96[8];
        v75 = v96[9];
        v76 = v96[10];
LABEL_273:
        *(_OWORD *)&MasterIrp[5].Overlay.AsynchronousParameters.UserApcRoutine = v75;
        *(_OWORD *)&MasterIrp[5].CancelRoutine = v76;
        if ( v88 )
          RefsDeleteMdlAndBuffer(v74, 0, v88);
        return;
      }
LABEL_257:
      Flink = 0;
      v91 = 0;
      v92 = 0;
      *(_DWORD *)&MasterIrp->Type = 1232;
      *(_QWORD *)(&MasterIrp->Size + 1) = 1;
      LODWORD(v81) = 0;
      if ( LODWORD(MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) == 16 )
        Flink = MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink->Flink;
      MasterIrp->UserIosb = (PIO_STATUS_BLOCK)(v87 & -(__int64)(BYTE4(v81) != 0));
      RefsScrubConvertMsScrubContextToScrubOutput((struct _SCRUB_DATA_INPUT *)MasterIrp, BYTE4(v81));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_iDLLD(
          WPP_GLOBAL_Control->AttachedDevice,
          *((unsigned __int8 *)&MasterIrp->Tail.CompletionKey + 76),
          WPP_GLOBAL_Control,
          Flink,
          MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink,
          *((unsigned __int8 *)&MasterIrp->Tail.CompletionKey + 76),
          *((unsigned __int8 *)&MasterIrp->Tail.CompletionKey + 77),
          WORD2(MasterIrp[5].MdlAddress->Next),
          v81);
      }
      *((_DWORD *)&MasterIrp->Tail.CompletionKey + 21) = MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink;
      v70 = v90;
      v90->IoStatus.Information = 192;
      v70->IoStatus.Information = 296;
      v70->IoStatus.Information = *((unsigned int *)&MasterIrp->Tail.CompletionKey + 21) + 296LL;
      LOWORD(MasterIrp->IoStatus.Information) = *((_WORD *)&MasterIrp->Tail.CompletionKey + 42) + 104;
      *(_DWORD *)(&MasterIrp->Size + 1) |= 0x40000u;
      v71 = (unsigned __int16 *)MasterIrp[5].MdlAddress;
      if ( v71[2] )
      {
        Information_low = LOWORD(v70->IoStatus.Information);
        v73 = 16LL * v71[2] + 8;
        memmove((char *)MasterIrp + Information_low, v71, v73);
        WORD1(MasterIrp->IoStatus.Information) = Information_low;
        *(_DWORD *)(&MasterIrp->Size + 1) |= 0x20000u;
        v70->IoStatus.Information += v73;
      }
      memset(v94, 0, sizeof(v94));
      LODWORD(v93) = 0;
      *((_QWORD *)&v93 + 1) = 0;
      *(_DWORD *)((char *)&v94[3] + 2) = 0;
      WORD3(v94[3]) = 0;
      MasterIrp[4].Tail.Overlay.DeviceQueueEntry.DeviceListEntry = 0;
      *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 1) = v93;
      *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 2) = v94[0];
      *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 3) = v94[1];
      *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 4) = v94[2];
      *((_OWORD *)&MasterIrp[4].Tail.CompletionKey + 5) = v94[3];
      *(_OWORD *)&MasterIrp[5].MdlAddress = v94[4];
      *(_OWORD *)&MasterIrp[5].AssociatedIrp.MasterIrp = v94[5];
      *(_OWORD *)&MasterIrp[5].ThreadListEntry.Blink = v94[6];
      *(_OWORD *)&MasterIrp[5].IoStatus.Information = v94[7];
      *(_OWORD *)&MasterIrp[5].UserIosb = v94[8];
      v75 = v94[9];
      v76 = v94[10];
      goto LABEL_273;
    }
    if ( (unsigned __int16)(*a4 - 2051) <= 1u )
    {
      BYTE4(v81) = 0;
      v32 = a1;
      v8 = MsScrubTable(a1[3], a3, *((_QWORD *)a4 + 52), &MasterIrp->Tail.CompletionKey + 9);
      goto LABEL_256;
    }
    BYTE4(v81) = 1;
    if ( (*((_DWORD *)a4 + 38) & 8) != 0 && (*((_DWORD *)a4 + 38) & 0x40) == 0 )
    {
      v8 = 0;
      goto LABEL_115;
    }
    if ( !*((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) || *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) == 1 )
    {
      v32 = a1;
      v8 = MsScrubTable(a1[3], a3, *(_QWORD *)(v91 + 264), &MasterIrp->Tail.CompletionKey + 9);
      if ( v8 < 0 )
        goto LABEL_115;
      if ( *((int *)&MasterIrp->Tail.CompletionKey + 20) <= 0
        || **(_BYTE **)a3
        || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread()) )
      {
        v8 = -2147483643;
        goto LABEL_256;
      }
      if ( (unsigned __int8)MsScrubContextFoundError(&MasterIrp->Tail.CompletionKey + 9)
        || (unsigned __int8)((__int64 (*)(void))MsScrubContextParityExtentDataFull)() )
      {
        goto LABEL_257;
      }
      *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) = 2;
      MsInitializeScrubKey(v63);
    }
    else
    {
      v32 = a1;
      if ( *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) != 2 && *((_BYTE *)&MasterIrp->Tail.CompletionKey + 77) != 4 )
        goto LABEL_256;
    }
    RefsCreateMdlAndBuffer((struct _IRP_CONTEXT *)v32, (struct _SCB *)v26, 2u, 1u, &v84, v23, &v88);
    v64 = (struct _FAST_MUTEX *)*((_QWORD *)a4 + 6);
    KeEnterGuardedRegion();
    ExAcquireFastMutexUnsafe(v64);
    _InterlockedAdd((volatile signed __int32 *)a4 + 43, 1u);
    v65 = *((_QWORD *)a4 + 3);
    ++*((_DWORD *)a4 + 43);
    ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)a4 + 6));
    KeLeaveGuardedRegion();
    v66 = ~(*(unsigned int *)(v85 + 276) - 1LL) & (v65 + (unsigned int)(*(_DWORD *)(v85 + 276) - 1));
    v87 = v66;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v67 = v86;
    }
    else
    {
      v67 = v86;
      WPP_SF_qDi(WPP_GLOBAL_Control->AttachedDevice, v66, v85, *((_QWORD *)v86 + 54), v84, v66);
      v66 = v87;
    }
    if ( (*(_DWORD *)(v91 + 152) & 0x20000) != 0 )
    {
      v83 = 1;
    }
    else
    {
      v83 = 0;
      if ( (*(_DWORD *)(&MasterIrp->Size + 1) & 0x10) == 0 )
      {
LABEL_249:
        if ( (*(_DWORD *)(&MasterIrp->Size + 1) & 8) != 0 )
          *((_DWORD *)&MasterIrp[4].Tail.CompletionKey + 8) |= 0x20u;
        v80 = (void **)v67;
        v68 = (CmsStream *)*((_QWORD *)v67 + 54);
        v32 = a1;
        v8 = MsScrubStream(
               a1[3],
               (struct _SmsCancelScrub *)a3,
               v68,
               v84,
               v66,
               v80,
               (struct _SmsScrubContext *)(&MasterIrp->Tail.CompletionKey + 9));
        if ( v83 || (*(_DWORD *)(&MasterIrp->Size + 1) & 0x10) != 0 )
          *((_DWORD *)&MasterIrp[4].Tail.CompletionKey + 8) &= ~2u;
        goto LABEL_256;
      }
    }
    *((_DWORD *)&MasterIrp[4].Tail.CompletionKey + 8) |= 2u;
    goto LABEL_249;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 457, &WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids, 3221225485LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v11 = 16544;
    goto LABEL_77;
  }
}

```

## disassembly

```asm
0x1402c072c  mov     r11, rsp
0x1402c072f  push    rbx
0x1402c0730  push    rsi
0x1402c0731  push    rdi
0x1402c0732  push    r12
0x1402c0734  push    r13
0x1402c0736  push    r14
0x1402c0738  push    r15
0x1402c073a  sub     rsp, 280h
0x1402c0741  mov     rax, cs:__security_cookie
0x1402c0748  xor     rax, rsp
0x1402c074b  mov     [rsp+2B8h+var_48], rax
0x1402c0753  mov     rdi, r9
0x1402c0756  mov     [rsp+2B8h+var_258], r9
0x1402c075b  mov     r12, r8
0x1402c075e  mov     rax, rdx
0x1402c0761  mov     [rsp+2B8h+var_238], rdx
0x1402c0769  mov     [rsp+2B8h+var_270], rcx
0x1402c076e  xor     r14d, r14d
0x1402c0771  mov     [rsp+2B8h+var_248], r14
0x1402c0776  mov     [rsp+2B8h+var_264], 100000h
0x1402c077e  mov     r8, [rdx+0B8h]
0x1402c0785  mov     [rsp+2B8h+var_240], r8
0x1402c078a  xorps   xmm0, xmm0
0x1402c078d  xor     ecx, ecx
0x1402c078f  movups  xmmword ptr [r11-80h], xmm0
0x1402c0794  movups  xmmword ptr [r11-70h], xmm0
0x1402c0799  movups  xmmword ptr [r11-60h], xmm0
0x1402c079e  mov     [r11-50h], rcx
0x1402c07a2  mov     edx, [r8+10h]
0x1402c07a6  cmp     edx, 0C0h
0x1402c07ac  jnb     short loc_1402C0808
0x1402c07ae  lea     rdi, WPP_GLOBAL_Control
0x1402c07b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c07bc  cmp     rcx, rdi
0x1402c07bf  jz      short loc_1402C07EF
0x1402c07c1  test    dword ptr [rcx+2Ch], 100h
0x1402c07c8  jz      short loc_1402C07EF
0x1402c07ca  lea     r13d, [r14+4]
0x1402c07ce  cmp     [rcx+29h], r13b
0x1402c07d2  jb      short loc_1402C07EF
0x1402c07d4  mov     edx, 1C8h
0x1402c07d9  mov     r9d, 0C000000Dh
0x1402c07df  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402c07e6  mov     rcx, [rcx+18h]
0x1402c07ea  call    WPP_SF_d
0x1402c07ef  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c07f5  test    al, al
0x1402c07f7  jz      loc_1402C0C25
0x1402c07fd  mov     r9d, 4097h
0x1402c0803  jmp     loc_1402C0C12
0x1402c0808  mov     r15, [rax+18h]
0x1402c080c  mov     r9d, 4D0h
0x1402c0812  cmp     [r15], r9d
0x1402c0815  jz      short loc_1402C0873
0x1402c0817  lea     rdi, WPP_GLOBAL_Control
0x1402c081e  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c0825  cmp     rcx, rdi
0x1402c0828  jz      short loc_1402C085A
0x1402c082a  test    dword ptr [rcx+2Ch], 100h
0x1402c0831  jz      short loc_1402C085A
0x1402c0833  mov     r13d, 4
0x1402c0839  cmp     [rcx+29h], r13b
0x1402c083d  jb      short loc_1402C085A
0x1402c083f  mov     edx, 1C9h
0x1402c0844  mov     r9d, 0C000000Dh
0x1402c084a  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402c0851  mov     rcx, [rcx+18h]
0x1402c0855  call    WPP_SF_d
0x1402c085a  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c0860  test    al, al
0x1402c0862  jz      loc_1402C0C25
0x1402c0868  mov     r9d, 40A0h
0x1402c086e  jmp     loc_1402C0C12
0x1402c0873  mov     rax, [rdi+90h]
0x1402c087a  mov     [rsp+2B8h+var_260], rax
0x1402c087f  lea     rbx, [r15+4]
0x1402c0883  mov     r10d, 2
0x1402c0889  cmp     [rax+188h], r10d
0x1402c0890  jnb     short loc_1402C0907
0x1402c0892  mov     eax, [rbx]
0x1402c0894  test    al, 8
0x1402c0896  jnz     short loc_1402C0907
0x1402c0898  lea     rdi, WPP_GLOBAL_Control
0x1402c089f  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c08a6  cmp     rcx, rdi
0x1402c08a9  jz      short loc_1402C08D9
0x1402c08ab  test    dword ptr [rcx+2Ch], 100h
0x1402c08b2  jz      short loc_1402C08D9
0x1402c08b4  lea     r13d, [r10+2]
0x1402c08b8  cmp     [rcx+29h], r13b
0x1402c08bc  jb      short loc_1402C08D9
0x1402c08be  mov     edx, 1CAh
0x1402c08c3  mov     r9d, 0C0000479h
0x1402c08c9  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402c08d0  mov     rcx, [rcx+18h]
0x1402c08d4  call    WPP_SF_d
0x1402c08d9  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c08df  test    al, al
0x1402c08e1  jz      short loc_1402C08FC
0x1402c08e3  mov     r9d, 40B1h; unsigned int
0x1402c08e9  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402c08f0  xor     edx, edx; struct _IRP_CONTEXT *
0x1402c08f2  mov     ecx, 0C0000479h; Status
0x1402c08f7  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402c08fc  mov     eax, 0C0000479h
0x1402c0901  jmp     loc_1402C1D24
0x1402c0907  lea     rsi, [r15+0C0h]
0x1402c090e  mov     ecx, [rbx]
0x1402c0910  mov     r11d, 1
0x1402c0916  and     ecx, r11d
0x1402c0919  jz      loc_1402C09E8
0x1402c091f  mov     eax, [rsi+0Ch]
0x1402c0922  cmp     eax, 280h
0x1402c0927  jbe     short loc_1402C0983
0x1402c0929  lea     rdi, WPP_GLOBAL_Control
0x1402c0930  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c0937  cmp     rcx, rdi
0x1402c093a  jz      short loc_1402C096A
0x1402c093c  test    dword ptr [rcx+2Ch], 100h
0x1402c0943  jz      short loc_1402C096A
0x1402c0945  lea     r13d, [r11+3]
0x1402c0949  cmp     [rcx+29h], r13b
0x1402c094d  jb      short loc_1402C096A
0x1402c094f  mov     edx, 1CBh
0x1402c0954  mov     r9d, 0C000000Dh
0x1402c095a  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402c0961  mov     rcx, [rcx+18h]
0x1402c0965  call    WPP_SF_d
0x1402c096a  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c0970  test    al, al
0x1402c0972  jz      loc_1402C0C25
0x1402c0978  mov     r9d, 40BDh
0x1402c097e  jmp     loc_1402C0C12
0x1402c0983  add     eax, 128h
0x1402c0988  cmp     edx, eax
0x1402c098a  jnb     short loc_1402C09E8
0x1402c098c  lea     rdi, WPP_GLOBAL_Control
0x1402c0993  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c099a  cmp     rcx, rdi
0x1402c099d  jz      short loc_1402C09CF
0x1402c099f  test    dword ptr [rcx+2Ch], 100h
0x1402c09a6  jz      short loc_1402C09CF
0x1402c09a8  mov     r13d, 4
0x1402c09ae  cmp     [rcx+29h], r13b
0x1402c09b2  jb      short loc_1402C09CF
0x1402c09b4  mov     edx, 1CCh
0x1402c09b9  mov     r9d, 0C000000Dh
0x1402c09bf  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402c09c6  mov     rcx, [rcx+18h]
0x1402c09ca  call    WPP_SF_d
0x1402c09cf  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c09d5  test    al, al
0x1402c09d7  jz      loc_1402C0C25
0x1402c09dd  mov     r9d, 40C5h
0x1402c09e3  jmp     loc_1402C0C12
0x1402c09e8  cmp     [r8+8], r9d
0x1402c09ec  jnb     short loc_1402C0A5E
0x1402c09ee  lea     rdi, WPP_GLOBAL_Control
0x1402c09f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c09fc  cmp     rcx, rdi
0x1402c09ff  jz      short loc_1402C0A31
0x1402c0a01  test    dword ptr [rcx+2Ch], 100h
0x1402c0a08  jz      short loc_1402C0A31
0x1402c0a0a  mov     r13d, 4
0x1402c0a10  cmp     [rcx+29h], r13b
0x1402c0a14  jb      short loc_1402C0A31
0x1402c0a16  mov     edx, 1CDh
0x1402c0a1b  mov     r9d, 0C0000023h
0x1402c0a21  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402c0a28  mov     rcx, [rcx+18h]
0x1402c0a2c  call    WPP_SF_d
0x1402c0a31  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c0a37  test    al, al
0x1402c0a39  jz      short loc_1402C0A54
0x1402c0a3b  mov     r9d, 40D0h; unsigned int
0x1402c0a41  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402c0a48  xor     edx, edx; struct _IRP_CONTEXT *
0x1402c0a4a  mov     ecx, 0C0000023h; Status
0x1402c0a4f  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402c0a54  mov     eax, 0C0000023h
0x1402c0a59  jmp     loc_1402C1D24
0x1402c0a5e  mov     rax, [rdi+88h]
0x1402c0a65  mov     [rsp+2B8h+var_230], rax
0x1402c0a6d  test    ecx, ecx
0x1402c0a6f  jz      loc_1402C0B07
0x1402c0a75  cmp     [rsi], r10d
0x1402c0a78  jnz     short loc_1402C0AAB
0x1402c0a7a  cmp     byte ptr [rsi+4], 16h
0x1402c0a7e  jnb     short loc_1402C0AAB
0x1402c0a80  cmp     byte ptr [rsi+5], 5
0x1402c0a84  jnb     short loc_1402C0AAB
0x1402c0a86  cmp     byte ptr [rsi+6], 0Ah
0x1402c0a8a  jnb     short loc_1402C0AAB
0x1402c0a8c  mov     eax, [rsi+0Ch]
0x1402c0a8f  cmp     eax, r9d
0x1402c0a92  ja      short loc_1402C0AAB
0x1402c0a94  lea     rcx, [rax+68h]
0x1402c0a98  add     rcx, rsi
0x1402c0a9b  lea     rax, [rsi+4D0h]
0x1402c0aa2  cmp     rcx, rax
0x1402c0aa5  jbe     loc_1402C0B31
0x1402c0aab  lea     rdi, WPP_GLOBAL_Control
0x1402c0ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c0ab9  cmp     rcx, rdi
0x1402c0abc  jz      short loc_1402C0AEE
0x1402c0abe  test    dword ptr [rcx+2Ch], 100h
0x1402c0ac5  jz      short loc_1402C0AEE
0x1402c0ac7  mov     r13d, 4
0x1402c0acd  cmp     [rcx+29h], r13b
0x1402c0ad1  jb      short loc_1402C0AEE
0x1402c0ad3  mov     edx, 1CEh
0x1402c0ad8  mov     r9d, 0C000000Dh
0x1402c0ade  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402c0ae5  mov     rcx, [rcx+18h]
0x1402c0ae9  call    WPP_SF_d
0x1402c0aee  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c0af4  test    al, al
0x1402c0af6  jz      loc_1402C0C25
0x1402c0afc  mov     r9d, 40E2h
0x1402c0b02  jmp     loc_1402C0C12
0x1402c0b07  mov     [rsi+4], r14w
0x1402c0b0c  mov     byte ptr [rsi+6], 9
0x1402c0b10  mov     rcx, rsi
0x1402c0b13  call    MsInitializeScrubKey
0x1402c0b18  lea     rcx, [rsi+18h]; void *
0x1402c0b1c  xor     edx, edx; Val
0x1402c0b1e  lea     r8d, [rdx+50h]; Size
0x1402c0b22  call    memset
0x1402c0b27  mov     r10d, 2
0x1402c0b2d  lea     r11d, [r10-1]
0x1402c0b31  mov     rdx, [r15+28h]
0x1402c0b35  mov     r13d, 4
0x1402c0b3b  test    rdx, rdx
0x1402c0b3e  jz      loc_1402C0CD2
0x1402c0b44  cmp     [rsp+2B8h+arg_20], r13b
0x1402c0b4c  jz      loc_1402C0C2F
0x1402c0b52  mov     r9d, 803h
0x1402c0b58  movzx   eax, word ptr [rdi]
0x1402c0b5b  sub     ax, r9w
0x1402c0b5f  cmp     ax, r11w
0x1402c0b63  jbe     loc_1402C0C2F
0x1402c0b69  mov     rax, [rdi+90h]
0x1402c0b70  mov     r8d, [rax+110h]
0x1402c0b77  lea     ecx, [r8-1]
0x1402c0b7b  test    [r15+20h], ecx
0x1402c0b7f  jnz     short loc_1402C0B93
0x1402c0b81  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1402c0b85  jz      loc_1402C0CD2
0x1402c0b8b  test    ecx, edx
0x1402c0b8d  jz      loc_1402C0CD2
0x1402c0b93  lea     rdi, WPP_GLOBAL_Control
0x1402c0b9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c0ba1  cmp     rcx, rdi
0x1402c0ba4  jz      short loc_1402C0BCC
0x1402c0ba6  test    dword ptr [rcx+2Ch], 400h
0x1402c0bad  jz      short loc_1402C0BCC
0x1402c0baf  cmp     [rcx+29h], r10b
0x1402c0bb3  jb      short loc_1402C0BCC
0x1402c0bb5  mov     dword ptr [rsp+2B8h+var_290], r8d
0x1402c0bba  mov     [rsp+2B8h+var_298], rdx
0x1402c0bbf  mov     r9, [r15+20h]
0x1402c0bc3  mov     rcx, [rcx+18h]
0x1402c0bc7  call    WPP_SF_iiD
0x1402c0bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c0bd3  cmp     rcx, rdi
0x1402c0bd6  jz      short loc_1402C0C02
0x1402c0bd8  test    dword ptr [rcx+2Ch], 100h
0x1402c0bdf  jz      short loc_1402C0C02
0x1402c0be1  cmp     [rcx+29h], r13b
0x1402c0be5  jb      short loc_1402C0C02
0x1402c0be7  mov     edx, 1D2h
0x1402c0bec  mov     r9d, 0C000000Dh
0x1402c0bf2  lea     r8, WPP_77d97c0dc6023b4e0651fac86ee6f331_Traceguids
0x1402c0bf9  mov     rcx, [rcx+18h]
0x1402c0bfd  call    WPP_SF_d
0x1402c0c02  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402c0c08  test    cl, cl
0x1402c0c0a  jz      short loc_1402C0C25
0x1402c0c0c  mov     r9d, 4113h; unsigned int
0x1402c0c12  lea     r8, aFsctrlC; "FsCtrl.c"
0x1402c0c19  xor     edx, edx; struct _IRP_CONTEXT *
0x1402c0c1b  mov     ecx, 0C000000Dh; Status
0x1402c0c20  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402c0c25  mov     eax, 0C000000Dh
0x1402c0c2a  jmp     loc_1402C1D24
0x1402c0c2f  lea     rdi, WPP_GLOBAL_Control
0x1402c0c36  mov     rcx, cs:WPP_GLOBAL_Control
0x1402c0c3d  cmp     rcx, rdi
0x1402c0c40  jz      short loc_1402C0C6F
0x1402c0c42  test    dword ptr [rcx+2Ch], 400h
0x1402c0c49  jz      short loc_1402C0C6F
0x1402c0c4b  cmp     [rcx+29h], r10b
0x1402c0c4f  jb      short loc_1402C0C6F
0x1402c0c51  mov     rbx, [rsp+2B8h+var_258]
0x1402c0c56  movsx   eax, word ptr [rbx]
0x1402c0c59  movzx   r9d, [rsp+2B8h+arg_20]
0x1402c0c62  mov     dword ptr [rsp+2B8h+var_298], eax
0x1402c0c66  mov     rcx, [rcx+18h]
0x1402c0c6a  call    WPP_SF_dD
  ... truncated ...
```
