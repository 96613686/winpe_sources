# USBSTOR_Scsi

- ea: `0x140004ed0`
- end: `0x140005d6c`
- name: `USBSTOR_Scsi`
- size: `3740`
- prototype: `__int64 __fastcall(PVOID Object, PIRP Irp)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003630`
- `0x140003b90`
- `0x140004ed0`
- `0x140005d80`
- `0x140005e50`
- `0x140006040`
- `0x140006910`
- `0x140007ff0`
- `0x14000b2e8`
- `0x14000b35c`
- `0x14000c96c`
- `0x14000cba8`
- `0x14000dd1c`
- `0x14000e120`
- `0x14000f39c`
- `0x1400104c8`
- `0x140010530`
- `0x1400105e8`
- `0x140010664`
- `0x140025630`

## import_xrefs

- `ntoskrnl!IoStartPacket` at `0x14000518c`
- `ntoskrnl!IoStartPacket` at `0x140005972`
- `ntoskrnl!IoStartPacket` at `0x140005d56`
- `ntoskrnl!IoStartPacket` at `0x14000518c`
- `ntoskrnl!IoStartPacket` at `0x140005972`
- `ntoskrnl!IoStartPacket` at `0x140005d56`
- `ntoskrnl!IofCompleteRequest` at `0x14000548a`
- `ntoskrnl!IofCompleteRequest` at `0x14000548a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004f85`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140005111`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400051e5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000539a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400054c0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400055d2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004f85`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140005111`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400051e5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000539a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400054c0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400055d2`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000554a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140005d0c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14000554a`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140005d0c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005064`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005890`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005064`
- `ntoskrnl!KeGetCurrentIrql` at `0x140005890`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400058a4`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1400058a4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004fe2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000516e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005245`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400053c6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000551d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000562f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004fe2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000516e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140005245`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400053c6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000551d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000562f`

## pseudocode

```c
__int64 __fastcall USBSTOR_Scsi(struct _DEVICE_OBJECT *Object, PIRP Irp)
{
  __int64 DeviceExtension; // rdi
  __int64 v5; // r13
  char v6; // r12
  __int64 v7; // r15
  int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // rax
  unsigned int v11; // ebx
  char v12; // r12
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rax
  NTSTATUS v17; // ebx
  __int64 v18; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  PDEVICE_OBJECT v22; // rcx
  char v23; // al
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 SecurityContext; // r13
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // r8
  PDEVICE_OBJECT v33; // rcx
  __int64 v34; // rdx
  IRP *v35; // rax
  _QWORD *v36; // rcx
  _QWORD *v37; // rax
  __int128 v38; // [rsp+30h] [rbp-40h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-30h] BYREF
  PULONG Key; // [rsp+A0h] [rbp+30h]
  struct _IO_STACK_LOCATION *v41; // [rsp+B0h] [rbp+40h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  DeviceExtension = (__int64)Object->DeviceExtension;
  if ( *(_DWORD *)DeviceExtension != 558842960 )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    memset(&LockHandle, 0, sizeof(LockHandle));
    SecurityContext = (__int64)CurrentStackLocation->Parameters.Create.SecurityContext;
    if ( P )
    {
      v29 = *(unsigned __int8 *)(SecurityContext + 2);
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 1230193491;
      *(_QWORD *)(qword_14001A190 + 8) = Object;
      *(_QWORD *)(qword_14001A190 + 16) = Irp;
      *(_QWORD *)(qword_14001A190 + 24) = v29;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v30 = qword_14001A198 - 32;
      else
        v30 = qword_14001A190 - 32;
      qword_14001A190 = v30;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( *(_BYTE *)(SecurityContext + 2) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      v17 = -1073741637;
    }
    else
    {
      v17 = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      if ( (unsigned __int8)IsRequestValid(Object, Irp) )
      {
        if ( (*(_DWORD *)(SecurityContext + 12) & 0x100000) == 0 || *(_DWORD *)(DeviceExtension + 156) == 1 )
        {
          Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
          *(_BYTE *)(SecurityContext + 3) = 0;
          USBSTOR_FxPowerReference(DeviceExtension, SecurityContext, 1);
          IoStartPacket(Object, Irp, (PULONG)(SecurityContext + 64), (PDRIVER_CANCEL)USBSTOR_CancelIo);
          v17 = 259;
          goto LABEL_34;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 70);
        }
        v17 = -1073741823;
        *(_BYTE *)(SecurityContext + 3) = 36;
      }
    }
    goto LABEL_72;
  }
  v5 = *(_QWORD *)(*(_QWORD *)(DeviceExtension + 16) + 64LL);
  v41 = Irp->Tail.Overlay.CurrentStackLocation;
  v6 = *(_BYTE *)(v5 + 2041);
  v7 = (__int64)v41->Parameters.Create.SecurityContext;
  if ( v6 == -1 )
  {
    v8 = *(_DWORD *)(v5 + 132);
    v6 = (v8 & 0x80u) != 0 && (v8 & 0x400) == 0;
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    v9 = *(unsigned __int8 *)(v7 + 2);
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1230193491;
    *(_QWORD *)(qword_14001A190 + 8) = Object;
    *(_QWORD *)(qword_14001A190 + 16) = Irp;
    *(_QWORD *)(qword_14001A190 + 24) = v9;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v10 = qword_14001A198 - 32;
    else
      v10 = qword_14001A190 - 32;
    qword_14001A190 = v10;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( *(_BYTE *)(v7 + 2) )
  {
    switch ( *(_BYTE *)(v7 + 2) )
    {
      case 1:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        if ( *(_BYTE *)(DeviceExtension + 68) )
        {
          v17 = -2147483631;
          v23 = 5;
          goto LABEL_71;
        }
        *(_BYTE *)(DeviceExtension + 68) = 1;
        *(_QWORD *)(v7 + 24) = Object;
        goto LABEL_69;
      case 4:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        v35 = (IRP *)UsbQueueRelease(DeviceExtension + 368);
        if ( !v35 )
          goto LABEL_61;
        IoStartPacket(
          *(PDEVICE_OBJECT *)(DeviceExtension + 16),
          v35,
          (PULONG)(v35->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId + 64),
          (PDRIVER_CANCEL)USBSTOR_CancelIo);
        *(_BYTE *)(v7 + 3) = 1;
        v17 = 0;
        goto LABEL_72;
      case 6:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        *(_BYTE *)(DeviceExtension + 68) = 0;
        v17 = 0;
        *(_BYTE *)(v7 + 3) = 1;
        goto LABEL_72;
      case 8:
        goto LABEL_94;
      case 0x15:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        memset(&LockHandle, 0, sizeof(LockHandle));
        v38 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
        }
        *((_QWORD *)&v38 + 1) = &v38;
        *(_QWORD *)&v38 = &v38;
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(DeviceExtension + 656), &LockHandle);
        *(_BYTE *)(DeviceExtension + 672) = 0;
        while ( 2 )
        {
          v20 = UsbDequeueIrp(DeviceExtension + 368);
          if ( v20 )
          {
            v36 = (_QWORD *)*((_QWORD *)&v38 + 1);
            if ( **((__int128 ***)&v38 + 1) == &v38 )
            {
              v37 = (_QWORD *)(v20 + 168);
              *v37 = &v38;
              v37[1] = v36;
              *v36 = v37;
              *((_QWORD *)&v38 + 1) = v37;
              continue;
            }
LABEL_189:
            __fastfail(3u);
          }
          break;
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        while ( 1 )
        {
          v21 = v38;
          if ( (__int128 *)v38 == &v38 )
            break;
          if ( *(__int128 **)(v38 + 8) != &v38 )
            goto LABEL_189;
          v26 = *(_QWORD *)v38;
          if ( *(_QWORD *)(*(_QWORD *)v38 + 8LL) != (_QWORD)v38 )
            goto LABEL_189;
          *(_QWORD *)&v38 = *(_QWORD *)v38;
          *(_QWORD *)(v26 + 8) = &v38;
          UsbCompleteFlushedIrp(Object, v21 - 168);
        }
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
LABEL_61:
          v17 = 0;
          *(_BYTE *)(v7 + 3) = 1;
        }
        else
        {
          v31 = 30;
          v32 = WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids;
LABEL_98:
          WPP_SF_(v22->AttachedDevice, v31, v32);
          *(_BYTE *)(v7 + 3) = 1;
          v17 = 0;
        }
        break;
      case 0x18:
        if ( v6 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
          }
          USBSTOR_LogEntry(1363953235, Object, Irp, *(unsigned __int8 *)(v7 + 2));
          UsbQueueFreeze(DeviceExtension + 368);
LABEL_69:
          v17 = 0;
          goto LABEL_70;
        }
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v34 = 58;
          goto LABEL_136;
        }
        goto LABEL_137;
      case 0x19:
        if ( v6 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
          }
          USBSTOR_LogEntry(1364543059, Object, Irp, *(unsigned __int8 *)(v7 + 2));
          UsbQueueUnFreeze(DeviceExtension + 368);
          if ( *(_DWORD *)(DeviceExtension + 372) && *(_DWORD *)(DeviceExtension + 48) == 1 )
          {
            UsbQueueRestart(Object);
            *(_BYTE *)(v7 + 3) = 1;
            v17 = 0;
            goto LABEL_72;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
          }
          *(_BYTE *)(v7 + 3) = 4;
LABEL_94:
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            v31 = 63;
            v32 = WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids;
            goto LABEL_98;
          }
        }
        goto LABEL_61;
      case 0x1A:
        if ( v6 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
          }
          USBSTOR_LogEntry(1146177107, Object, Irp, *(unsigned __int8 *)(v7 + 2));
          v17 = USBSTOR_PdoQuiesceDevice(Object);
LABEL_70:
          v23 = 1;
        }
        else
        {
          v33 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            v34 = 60;
LABEL_136:
            WPP_SF_(v33->AttachedDevice, v34, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
          }
LABEL_137:
          v17 = -1073741637;
          v23 = 4;
        }
LABEL_71:
        *(_BYTE *)(v7 + 3) = v23;
        if ( v17 != 259 )
          goto LABEL_72;
        goto LABEL_34;
      default:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        *(_BYTE *)(v7 + 3) = 4;
        v17 = -1073741637;
        goto LABEL_72;
    }
    goto LABEL_72;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  if ( !(unsigned __int8)IsRequestValid(Object, Irp) )
  {
    v17 = -1073741811;
    goto LABEL_72;
  }
  if ( (unsigned int)(*(_DWORD *)(DeviceExtension + 40) - 7) <= 1 )
  {
    *(_BYTE *)(v7 + 3) = 8;
    v17 = -1073741810;
    goto LABEL_72;
  }
  if ( (*(_DWORD *)(v7 + 12) & 0x100000) != 0 )
  {
    if ( *(_DWORD *)(DeviceExtension + 48) != 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 55);
      }
      *(_BYTE *)(v7 + 3) = 36;
      v17 = -1073741823;
      goto LABEL_72;
    }
    if ( *(_BYTE *)(DeviceExtension + 672) )
    {
      *(_BYTE *)(v7 + 3) = 5;
      v17 = -1073741823;
      goto LABEL_72;
    }
  }
  v11 = 0;
  *(_BYTE *)(v7 + 3) = 0;
  if ( *(_BYTE *)(v7 + 72) == 26 )
  {
    Key = *(PULONG *)(*(_QWORD *)(DeviceExtension + 16) + 64LL);
    if ( !KeGetCurrentIrql() )
      USBSTOR_GetWriteProtectSetting((__int64)Key);
  }
  v41->Parameters.QueryDirectory.FileName = (PUNICODE_STRING)DeviceExtension;
  if ( v6 )
  {
    if ( (*(_DWORD *)(v7 + 12) & 0x80010) != 0 && *(_BYTE *)(DeviceExtension + 672) )
    {
      if ( !(unsigned __int8)USBSTOR_ClaimCurrentSrb(v5) )
      {
        *(_BYTE *)(v7 + 3) = 5;
        v17 = -2147483631;
        goto LABEL_72;
      }
      v11 = 1;
    }
    else if ( *(_DWORD *)(v5 + 156) == 4 )
    {
      v11 = 2;
    }
  }
  USBSTOR_FxPowerReference(v5, v7, 1);
  v12 = 0;
  if ( *(_BYTE *)(v5 + 1876) && (*(_DWORD *)(v7 + 12) & 0x40000000) != 0 && KeGetCurrentIrql() < 2u )
  {
    KeEnterGuardedRegion();
    v12 = 1;
  }
  if ( (unsigned __int8)UsbQueueInsert(DeviceExtension + 368, Irp, *(unsigned int *)(v7 + 64), v11) )
  {
    if ( v11 != 1 )
    {
      if ( v11 == 2
        && (*(_DWORD *)(v5 + 128) & 0x10) != 0
        && *(_DWORD *)(DeviceExtension + 668) < *(_DWORD *)(DeviceExtension + 664)
        && !*(_BYTE *)(DeviceExtension + 672) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqq(
            WPP_GLOBAL_Control->AttachedDevice,
            v13,
            v14,
            *(_QWORD *)(DeviceExtension + 16),
            DeviceExtension + 368,
            Irp);
        }
        USBSTOR_LogEntry(1230521681, Object, Irp, *(_QWORD *)(DeviceExtension + 16));
        UsbStorPumpNextRequest(DeviceExtension);
        UsbStorStartNextPacket(*(PDEVICE_OBJECT *)(DeviceExtension + 16));
      }
      goto LABEL_31;
    }
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      v24 = *(_QWORD *)(DeviceExtension + 16);
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 844120657;
      *(_QWORD *)(qword_14001A190 + 8) = Object;
      *(_QWORD *)(qword_14001A190 + 16) = Irp;
      *(_QWORD *)(qword_14001A190 + 24) = v24;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v25 = qword_14001A198 - 32;
      else
        v25 = qword_14001A190 - 32;
      qword_14001A190 = v25;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    *(_BYTE *)(v7 + 3) = 5;
    v17 = -2147483631;
    USBSTOR_FxPowerReference(v5, v7, 0);
    if ( v12 )
      KeLeaveGuardedRegion();
LABEL_72:
    Irp->IoStatus.Status = v17;
    IofCompleteRequest(Irp, 0);
    goto LABEL_34;
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    v15 = *(_QWORD *)(DeviceExtension + 16);
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1347637065;
    *(_QWORD *)(qword_14001A190 + 8) = Object;
    *(_QWORD *)(qword_14001A190 + 16) = Irp;
    *(_QWORD *)(qword_14001A190 + 24) = v15;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v16 = qword_14001A198 - 32;
    else
      v16 = qword_14001A190 - 32;
    qword_14001A190 = v16;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  IoStartPacket(*(PDEVICE_OBJECT *)(DeviceExtension + 16), Irp, (PULONG)(v7 + 64), (PDRIVER_CANCEL)USBSTOR_CancelIo);
LABEL_31:
  if ( v12 )
    KeLeaveGuardedRegion();
  v17 = 259;
LABEL_34:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1769169779;
    *(_QWORD *)(qword_14001A190 + 8) = v17;
    *(_QWORD *)(qword_14001A190 + 16) = Object;
    *(_QWORD *)(qword_14001A190 + 24) = Irp;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v18 = qword_14001A198 - 32;
    else
      v18 = qword_14001A190 - 32;
    qword_14001A190 = v18;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140004ed0  push    rbp
0x140004ed2  push    rbx
0x140004ed3  push    rsi
0x140004ed4  push    rdi
0x140004ed5  push    r14
0x140004ed7  mov     rbp, rsp
0x140004eda  sub     rsp, 70h
0x140004ede  mov     rsi, rdx
0x140004ee1  mov     r14, rcx
0x140004ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x140004eeb  lea     rbx, WPP_GLOBAL_Control
0x140004ef2  cmp     rcx, rbx
0x140004ef5  jz      short loc_140004F02
0x140004ef7  mov     eax, [rcx+2Ch]
0x140004efa  test    al, 1
0x140004efc  jnz     loc_140005C73
0x140004f02  mov     rdi, [r14+40h]
0x140004f06  mov     [rsp+70h+arg_8], r12
0x140004f0e  mov     [rsp+70h+var_8], r13
0x140004f13  mov     [rsp+70h+var_10], r15
0x140004f18  cmp     dword ptr [rdi], 214F4450h
0x140004f1e  jnz     loc_14000559D
0x140004f24  mov     rax, [rdi+10h]
0x140004f28  mov     r13, [rax+40h]
0x140004f2c  mov     rax, [rsi+0B8h]
0x140004f33  mov     [rbp+arg_10], rax
0x140004f37  movzx   r12d, byte ptr [r13+7F9h]
0x140004f3f  mov     r15, [rax+8]
0x140004f43  cmp     r12b, 0FFh
0x140004f47  jnz     short loc_140004F5B
0x140004f49  mov     eax, [r13+84h]
0x140004f50  test    al, al
0x140004f52  js      loc_140005C97
0x140004f58  xor     r12b, r12b
0x140004f5b  xor     eax, eax
0x140004f5d  xorps   xmm0, xmm0
0x140004f60  cmp     cs:P, rax
0x140004f67  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140004f6b  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140004f6f  jz      loc_140004FF5
0x140004f75  movzx   ebx, byte ptr [r15+2]
0x140004f7a  lea     rdx, [rbp+LockHandle]; LockHandle
0x140004f7e  lea     rcx, SpinLock; SpinLock
0x140004f85  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140004f8c  nop     dword ptr [rax+rax+00h]
0x140004f91  mov     rax, cs:qword_14001A190
0x140004f98  mov     dword ptr [rax], 49534353h
0x140004f9e  mov     rax, cs:qword_14001A190
0x140004fa5  mov     [rax+8], r14
0x140004fa9  mov     rax, cs:qword_14001A190
0x140004fb0  mov     [rax+10h], rsi
0x140004fb4  mov     rax, cs:qword_14001A190
0x140004fbb  mov     [rax+18h], rbx
0x140004fbf  mov     rax, cs:qword_14001A190
0x140004fc6  cmp     rax, cs:P
0x140004fcd  jbe     loc_140005ACE
0x140004fd3  sub     rax, 20h ; ' '
0x140004fd7  lea     rcx, [rbp+LockHandle]; LockHandle
0x140004fdb  mov     cs:qword_14001A190, rax
0x140004fe2  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140004fe9  nop     dword ptr [rax+rax+00h]
0x140004fee  lea     rbx, WPP_GLOBAL_Control
0x140004ff5  movzx   r9d, byte ptr [r15+2]
0x140004ffa  test    r9d, r9d
0x140004ffd  jnz     loc_140005319
0x140005003  mov     rcx, cs:WPP_GLOBAL_Control
0x14000500a  cmp     rcx, rbx
0x14000500d  jz      short loc_14000501A
0x14000500f  mov     eax, [rcx+2Ch]
0x140005012  test    al, 1
0x140005014  jnz     loc_140005A12
0x14000501a  mov     rdx, rsi
0x14000501d  mov     rcx, r14
0x140005020  call    IsRequestValid
0x140005025  test    al, al
0x140005027  jz      loc_140005D1D
0x14000502d  mov     eax, [rdi+28h]
0x140005030  sub     eax, 7
0x140005033  cmp     eax, 1
0x140005036  jbe     loc_140005C2C
0x14000503c  mov     r9d, [r15+0Ch]
0x140005040  bt      r9d, 14h
0x140005045  jb      loc_1400056EE
0x14000504b  xor     ebx, ebx
0x14000504d  mov     [r15+3], bl
0x140005051  cmp     byte ptr [r15+48h], 1Ah
0x140005056  jnz     short loc_14000507D
0x140005058  mov     rax, [rdi+10h]
0x14000505c  mov     rax, [rax+40h]
0x140005060  mov     [rbp+Key], rax
0x140005064  call    cs:__imp_KeGetCurrentIrql
0x14000506b  nop     dword ptr [rax+rax+00h]
0x140005070  test    al, al
0x140005072  jnz     short loc_14000507D
0x140005074  mov     rcx, [rbp+Key]
0x140005078  call    USBSTOR_GetWriteProtectSetting
0x14000507d  mov     rax, [rbp+arg_10]
0x140005081  mov     [rax+10h], rdi
0x140005085  test    r12b, r12b
0x140005088  jz      short loc_1400050A8
0x14000508a  test    dword ptr [r15+0Ch], 80010h
0x140005092  jnz     loc_1400057D8
0x140005098  cmp     dword ptr [r13+9Ch], 4
0x1400050a0  mov     eax, 2
0x1400050a5  cmovz   ebx, eax
0x1400050a8  mov     r8b, 1
0x1400050ab  mov     rdx, r15
0x1400050ae  mov     rcx, r13
0x1400050b1  call    USBSTOR_FxPowerReference
0x1400050b6  xor     r12b, r12b
0x1400050b9  cmp     [r13+754h], r12b
0x1400050c0  jnz     loc_140005882
0x1400050c6  mov     r8d, [r15+40h]
0x1400050ca  lea     rax, [r15+40h]
0x1400050ce  lea     rcx, [rdi+170h]
0x1400050d5  mov     [rbp+Key], rax
0x1400050d9  mov     r9d, ebx
0x1400050dc  mov     rdx, rsi
0x1400050df  call    UsbQueueInsert
0x1400050e4  test    al, al
0x1400050e6  jnz     loc_140005271
0x1400050ec  xor     eax, eax
0x1400050ee  xorps   xmm0, xmm0
0x1400050f1  cmp     cs:P, rax
0x1400050f8  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400050fc  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140005100  jz      short loc_14000517A
0x140005102  mov     rbx, [rdi+10h]
0x140005106  lea     rdx, [rbp+LockHandle]; LockHandle
0x14000510a  lea     rcx, SpinLock; SpinLock
0x140005111  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140005118  nop     dword ptr [rax+rax+00h]
0x14000511d  mov     rax, cs:qword_14001A190
0x140005124  mov     dword ptr [rax], 50534F49h
0x14000512a  mov     rax, cs:qword_14001A190
0x140005131  mov     [rax+8], r14
0x140005135  mov     rax, cs:qword_14001A190
0x14000513c  mov     [rax+10h], rsi
0x140005140  mov     rax, cs:qword_14001A190
0x140005147  mov     [rax+18h], rbx
0x14000514b  mov     rax, cs:qword_14001A190
0x140005152  cmp     rax, cs:P
0x140005159  jbe     loc_140005BCD
0x14000515f  sub     rax, 20h ; ' '
0x140005163  lea     rcx, [rbp+LockHandle]; LockHandle
0x140005167  mov     cs:qword_14001A190, rax
0x14000516e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140005175  nop     dword ptr [rax+rax+00h]
0x14000517a  mov     r8, [rbp+Key]; Key
0x14000517e  lea     r9, USBSTOR_CancelIo; CancelFunction
0x140005185  mov     rcx, [rdi+10h]; DeviceObject
0x140005189  mov     rdx, rsi; Irp
0x14000518c  call    cs:__imp_IoStartPacket
0x140005193  nop     dword ptr [rax+rax+00h]
0x140005198  lea     r15, WPP_GLOBAL_Control
0x14000519f  test    r12b, r12b
0x1400051a2  jnz     loc_140005D0C
0x1400051a8  mov     ebx, 103h
0x1400051ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400051b4  cmp     rcx, r15
0x1400051b7  jz      short loc_1400051C4
0x1400051b9  mov     eax, [rcx+2Ch]
0x1400051bc  test    al, 1
0x1400051be  jnz     loc_140005A97
0x1400051c4  xor     eax, eax
0x1400051c6  xorps   xmm0, xmm0
0x1400051c9  cmp     cs:P, rax
0x1400051d0  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400051d4  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400051d8  jz      short loc_140005251
0x1400051da  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400051de  lea     rcx, SpinLock; SpinLock
0x1400051e5  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400051ec  nop     dword ptr [rax+rax+00h]
0x1400051f1  mov     rax, cs:qword_14001A190
0x1400051f8  movsxd  rcx, ebx
0x1400051fb  mov     dword ptr [rax], 69736373h
0x140005201  mov     rax, cs:qword_14001A190
0x140005208  mov     [rax+8], rcx
0x14000520c  mov     rax, cs:qword_14001A190
0x140005213  mov     [rax+10h], r14
0x140005217  mov     rax, cs:qword_14001A190
0x14000521e  mov     [rax+18h], rsi
0x140005222  mov     rax, cs:qword_14001A190
0x140005229  cmp     rax, cs:P
0x140005230  jbe     loc_140005ABE
0x140005236  sub     rax, 20h ; ' '
0x14000523a  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000523e  mov     cs:qword_14001A190, rax
0x140005245  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000524c  nop     dword ptr [rax+rax+00h]
0x140005251  mov     r15, [rsp+70h+var_10]
0x140005256  mov     eax, ebx
0x140005258  mov     r13, [rsp+70h+var_8]
0x14000525d  mov     r12, [rsp+70h+arg_8]
0x140005265  add     rsp, 70h
0x140005269  pop     r14
0x14000526b  pop     rdi
0x14000526c  pop     rsi
0x14000526d  pop     rbx
0x14000526e  pop     rbp
0x14000526f  retn
0x140005271  cmp     ebx, 1
0x140005274  jz      loc_14000549B
0x14000527a  cmp     ebx, 2
0x14000527d  jnz     loc_140005198
0x140005283  mov     eax, [r13+80h]
0x14000528a  test    al, 10h
0x14000528c  jz      loc_140005198
0x140005292  mov     eax, [rdi+298h]
0x140005298  cmp     [rdi+29Ch], eax
0x14000529e  jge     loc_140005198
0x1400052a4  cmp     byte ptr [rdi+2A0h], 0
0x1400052ab  jnz     loc_140005198
0x1400052b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052b8  lea     r15, WPP_GLOBAL_Control
0x1400052bf  cmp     rcx, r15
0x1400052c2  jz      short loc_1400052EF
0x1400052c4  mov     eax, [rcx+2Ch]
0x1400052c7  test    al, 1
0x1400052c9  jz      short loc_1400052EF
0x1400052cb  cmp     byte ptr [rcx+29h], 4
0x1400052cf  jb      short loc_1400052EF
0x1400052d1  mov     r9, [rdi+10h]
0x1400052d5  lea     rax, [rdi+170h]
0x1400052dc  mov     rcx, [rcx+18h]
0x1400052e0  mov     [rsp+70h+var_48], rsi
0x1400052e5  mov     [rsp+70h+var_50], rax
0x1400052ea  call    WPP_SF_qqq
0x1400052ef  mov     r9, [rdi+10h]
0x1400052f3  mov     r8, rsi
0x1400052f6  mov     rdx, r14
0x1400052f9  mov     ecx, 49584551h
0x1400052fe  call    USBSTOR_LogEntry
0x140005303  mov     rcx, rdi
0x140005306  call    UsbStorPumpNextRequest
0x14000530b  mov     rcx, [rdi+10h]; DeviceObject
0x14000530f  call    UsbStorStartNextPacket
0x140005314  jmp     loc_14000519F
0x140005319  lea     eax, [r9-1]; switch 26 cases
0x14000531d  cmp     eax, 19h
0x140005320  ja      def_140005341; jumptable 0000000140005341 default case, cases 2,3,5,7,9-20,22,23
0x140005326  lea     rdx, cs:140000000h
0x14000532d  cdqe
0x14000532f  movzx   eax, ds:(byte_1400178FD - 140000000h)[rdx+rax]
0x140005337  mov     ecx, ds:(jpt_140005341 - 140000000h)[rdx+rax*4]
0x14000533e  add     rcx, rdx
0x140005341  jmp     rcx; switch jump
0x140005347  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000140005341 case 21
0x14000534e  cmp     rcx, rbx
0x140005351  jnz     loc_14000571F
0x140005357  xorps   xmm0, xmm0
0x14000535a  xor     eax, eax
0x14000535c  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140005360  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140005364  movups  [rbp+var_40], xmm0
0x140005368  mov     rcx, cs:WPP_GLOBAL_Control
0x14000536f  cmp     rcx, rbx
0x140005372  jz      short loc_14000537F
0x140005374  mov     eax, [rcx+2Ch]
0x140005377  test    al, 20h
0x140005379  jnz     loc_140005CA9
0x14000537f  lea     rax, [rbp+var_40]
0x140005383  mov     qword ptr [rbp+var_40+8], rax
0x140005387  lea     rcx, [rdi+290h]; SpinLock
0x14000538e  lea     rax, [rbp+var_40]
0x140005392  lea     rdx, [rbp+LockHandle]; LockHandle
0x140005396  mov     qword ptr [rbp+var_40], rax
0x14000539a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400053a1  nop     dword ptr [rax+rax+00h]
0x1400053a6  mov     byte ptr [rdi+2A0h], 0
0x1400053ad  lea     rcx, [rdi+170h]
0x1400053b4  call    UsbDequeueIrp
0x1400053b9  test    rax, rax
0x1400053bc  jnz     loc_140005C42
0x1400053c2  lea     rcx, [rbp+LockHandle]; LockHandle
0x1400053c6  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400053cd  nop     dword ptr [rax+rax+00h]
0x1400053d2  mov     rdx, qword ptr [rbp+var_40]
0x1400053d6  lea     rax, [rbp+var_40]
0x1400053da  cmp     rdx, rax
0x1400053dd  jnz     loc_140005562
0x1400053e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400053ea  cmp     rcx, rbx
0x1400053ed  jz      short loc_1400053FA
0x1400053ef  mov     eax, [rcx+2Ch]
0x1400053f2  test    al, 20h
0x1400053f4  jnz     loc_140005CCD
0x1400053fa  xor     ebx, ebx
0x1400053fc  mov     byte ptr [r15+3], 1
0x140005401  lea     r15, WPP_GLOBAL_Control
0x140005408  jmp     short loc_140005482
0x14000540a  test    r12b, r12b; jumptable 0000000140005341 case 24
0x14000540d  jz      loc_1400058B8
0x140005413  mov     rcx, cs:WPP_GLOBAL_Control
0x14000541a  cmp     rcx, rbx
0x14000541d  jz      short loc_140005441
0x14000541f  mov     eax, [rcx+2Ch]
0x140005422  test    al, 1
0x140005424  jz      short loc_140005441
  ... truncated ...
```
