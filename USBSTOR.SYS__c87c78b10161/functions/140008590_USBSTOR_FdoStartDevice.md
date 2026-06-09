# USBSTOR_FdoStartDevice

- ea: `0x140008590`
- end: `0x14000909f`
- name: `USBSTOR_FdoStartDevice`
- size: `2831`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140008590`
- `0x1400090a8`
- `0x14000a84c`
- `0x14000fee8`
- `0x1400105e8`
- `0x140010664`
- `0x14001100c`
- `0x140012318`
- `0x140013990`
- `0x14001f0ec`
- `0x14001f4bc`
- `0x140025738`
- `0x140026f6c`
- `0x1400279c0`
- `0x140028098`
- `0x140028344`
- `0x140029134`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140008b7b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140008b7b`
- `ntoskrnl!IoAllocateMdl` at `0x1400088f5`
- `ntoskrnl!IoAllocateMdl` at `0x1400088f5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000879a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000885b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000879a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000885b`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140008689`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140008689`
- `ntoskrnl!ExAllocatePool2` at `0x140008777`
- `ntoskrnl!ExAllocatePool2` at `0x140008777`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000886c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000886c`
- `ntoskrnl!IoAllocateWorkItem` at `0x140008b93`
- `ntoskrnl!IoAllocateWorkItem` at `0x140008d99`
- `ntoskrnl!IoAllocateWorkItem` at `0x140008efd`
- `ntoskrnl!IoAllocateWorkItem` at `0x140008b93`
- `ntoskrnl!IoAllocateWorkItem` at `0x140008d99`
- `ntoskrnl!IoAllocateWorkItem` at `0x140008efd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400088b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400088b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008e2a`
- `ntoskrnl!IofCompleteRequest` at `0x140008a03`
- `ntoskrnl!IofCompleteRequest` at `0x140008a03`
- `ntoskrnl!ZwClose` at `0x14000889f`
- `ntoskrnl!ZwClose` at `0x14000889f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000860d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000896b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140008a4a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000860d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000896b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140008a4a`
- `ntoskrnl!IoStartNextPacket` at `0x1400089dc`
- `ntoskrnl!IoStartNextPacket` at `0x1400089dc`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008923`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008923`
- `ntoskrnl!KeLowerIrql` at `0x140008b37`
- `ntoskrnl!KeLowerIrql` at `0x140008b37`
- `ntoskrnl!KfRaiseIrql` at `0x140008ad7`
- `ntoskrnl!KfRaiseIrql` at `0x140008ad7`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000888b`
- `ntoskrnl!ZwOpenKey` at `0x1400087d7`
- `ntoskrnl!ZwOpenKey` at `0x1400087d7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000866b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400089cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008aab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000866b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400089cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140008aab`
- `ntoskrnl!DbgPrintEx` at `0x140008fbe`
- `ntoskrnl!DbgPrintEx` at `0x140008fbe`

## string_xrefs

- `0x1400087f0`: `RtlQueryRegistryValuesEx`
- `0x14000878f`: `\Registry\Machine\Software\Policies\Microsoft\Windows\EnhancedStorageDevices`
- `0x140008fb0`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`

## pseudocode

```c
__int64 __fastcall USBSTOR_FdoStartDevice(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char v2; // r12
  __int64 v5; // rax
  char *DeviceExtension; // rbx
  struct _DEVICE_OBJECT *v7; // rcx
  IO_STATUS_BLOCK *p_IoStatus; // r15
  int Status; // edi
  __int64 v10; // rcx
  int v11; // r8d
  __int64 v12; // rdx
  __int64 Pool2; // r13
  char *v14; // rax
  char *v15; // rax
  void *v16; // rdi
  PVOID SystemRoutineAddress; // rax
  struct _MDL *Mdl; // rax
  KIRQL v19; // r13
  __int64 v20; // rax
  __int64 v21; // rax
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  PIO_WORKITEM WorkItem; // rax
  __int64 v26; // rax
  _WORD *v27; // rax
  __int64 v28; // r8
  ULONG v29; // r9d
  const GUID *v30; // rdx
  ULONG v31; // r8d
  UCHAR *v32; // r9
  PIO_WORKITEM v33; // rax
  USBD_HANDLE v34; // r13
  void (__fastcall *v35)(_QWORD); // rax
  PIO_WORKITEM v36; // rax
  const char *v37; // r9
  unsigned int v38; // eax
  ULONG *Irpa; // [rsp+20h] [rbp-E0h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B0h]
  char *v42; // [rsp+58h] [rbp-A8h]
  int v43; // [rsp+60h] [rbp-A0h]
  __int128 v44; // [rsp+64h] [rbp-9Ch]
  int v45; // [rsp+74h] [rbp-8Ch]
  __int64 v46; // [rsp+78h] [rbp-88h]
  char *v47; // [rsp+80h] [rbp-80h]
  int v48; // [rsp+88h] [rbp-78h]
  __int128 v49; // [rsp+8Ch] [rbp-74h]
  int v50; // [rsp+9Ch] [rbp-64h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v53; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v54; // [rsp+F0h] [rbp-10h]
  __int128 v55; // [rsp+100h] [rbp+0h]
  __int128 v56; // [rsp+110h] [rbp+10h]
  __int64 (__fastcall *v57)(_QWORD); // [rsp+120h] [rbp+20h]
  void *KeyHandle; // [rsp+170h] [rbp+70h] BYREF
  USBD_HANDLE USBDHandle; // [rsp+178h] [rbp+78h] BYREF

  v2 = 0;
  v57 = 0;
  USBDHandle = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1414681683;
    *(_QWORD *)(qword_14001A190 + 8) = DeviceObject;
    *(_QWORD *)(qword_14001A190 + 16) = Irp;
    *(_QWORD *)(qword_14001A190 + 24) = 0;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v5 = qword_14001A198 - 32;
    else
      v5 = qword_14001A190 - 32;
    qword_14001A190 = v5;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v7 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 3);
  DeviceExtension[1865] = 0;
  p_IoStatus = &Irp->IoStatus;
  if ( !IoForwardIrpSynchronously(v7, Irp) )
  {
    Status = -1073741823;
LABEL_43:
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_23;
    }
    v24 = 57;
LABEL_47:
    WPP_SF_(v23->AttachedDevice, v24, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    goto LABEL_23;
  }
  Status = p_IoStatus->Status;
  if ( p_IoStatus->Status < 0 )
    goto LABEL_43;
  v41 = 1;
  *(_QWORD *)&v44 = 0;
  *((_DWORD *)DeviceExtension + 467) = 0;
  *((_DWORD *)DeviceExtension + 468) = 0;
  v42 = DeviceExtension + 1868;
  v47 = DeviceExtension + 1872;
  v10 = 0;
  *((_QWORD *)&v44 + 1) = 0;
  v45 = 0;
  v11 = 0;
  v46 = 2;
  v12 = 0;
  v49 = 0u;
  v50 = 0;
  v43 = 4;
  v48 = 4;
  memset(&ObjectAttributes, 0, 44);
  KeyHandle = 0;
  DestinationString = 0;
  do
  {
    if ( *(_DWORD *)((char *)&v41 + v10) == 1 )
    {
      *(_QWORD *)((char *)&v44 + v10 + 4) = L"RootHubConnectedEnStorDevices";
LABEL_11:
      *(_DWORD *)((char *)&v44 + v10 + 12) = 67108868;
      goto LABEL_12;
    }
    if ( *(_DWORD *)((char *)&v41 + v10) == 2 )
    {
      *(_QWORD *)((char *)&v44 + v10 + 4) = L"DisallowLegacyDiskDevices";
      goto LABEL_11;
    }
    v11 = -1073741811;
LABEL_12:
    ++v12;
    v10 += 40;
  }
  while ( v12 != 2 );
  if ( v11 >= 0 )
  {
    Pool2 = ExAllocatePool2(256, 168, 1396788565);
    if ( Pool2 )
    {
      RtlInitUnicodeString(
        &DestinationString,
        L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\EnhancedStorageDevices");
      *(_QWORD *)&ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_QWORD *)&ObjectAttributes.Attributes = 576;
      ObjectAttributes.RootDirectory = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        *(_QWORD *)(Pool2 + 16) = *(_QWORD *)((char *)&v44 + 4);
        v14 = v42;
        *(_QWORD *)(Pool2 + 24) = v42;
        *(_QWORD *)(Pool2 + 40) = v14;
        *(_DWORD *)(Pool2 + 48) = v43;
        *(_DWORD *)(Pool2 + 32) = HIDWORD(v44);
        *(_QWORD *)(Pool2 + 72) = *(_QWORD *)((char *)&v49 + 4);
        v15 = v47;
        *(_QWORD *)(Pool2 + 80) = v47;
        *(_QWORD *)(Pool2 + 96) = v15;
        *(_DWORD *)(Pool2 + 104) = v48;
        *(_DWORD *)(Pool2 + 88) = HIDWORD(v49);
        *(_DWORD *)(Pool2 + 8) = 288;
        *(_DWORD *)(Pool2 + 64) = 288;
        v16 = KeyHandle;
        LockHandle.LockQueue = 0;
        RtlInitUnicodeString((PUNICODE_STRING)&LockHandle, L"RtlQueryRegistryValuesEx");
        SystemRoutineAddress = MmGetSystemRoutineAddress((PUNICODE_STRING)&LockHandle);
        if ( !SystemRoutineAddress )
          SystemRoutineAddress = RtlQueryRegistryValues;
        ((void (__fastcall *)(__int64, void *, __int64, _QWORD, _QWORD))SystemRoutineAddress)(
          0x40000000,
          v16,
          Pool2,
          0,
          0);
        ZwClose(KeyHandle);
      }
      ExFreePoolWithTag((PVOID)Pool2, 0);
    }
  }
  DeviceExtension[1866] = USBSTOR_IsDeviceConnectedToRootHub(DeviceObject);
  if ( !*((_QWORD *)DeviceExtension + 213) )
  {
    Mdl = IoAllocateMdl(DeviceExtension + 1192, 0x200u, 0, 0, 0);
    *((_QWORD *)DeviceExtension + 213) = Mdl;
    if ( !Mdl )
    {
      Status = -1073741670;
      goto LABEL_23;
    }
    MmBuildMdlForNonPagedPool(Mdl);
  }
  if ( !*((_QWORD *)DeviceExtension + 46) )
  {
    WorkItem = IoAllocateWorkItem(DeviceObject);
    *((_QWORD *)DeviceExtension + 46) = WorkItem;
    if ( !WorkItem )
    {
      Status = -1073741670;
      goto LABEL_23;
    }
  }
  if ( !*((_QWORD *)DeviceExtension + 6) )
  {
    Status = USBSTOR_GetDescriptors(DeviceObject);
    if ( Status < 0 )
    {
LABEL_23:
      if ( DeviceExtension[1932] )
        goto LABEL_24;
      goto LABEL_35;
    }
  }
  USBSTOR_QueryGlobalFdoParams((__int64)DeviceObject);
  Status = USBSTOR_SelectConfiguration(DeviceObject);
  if ( Status < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_23;
    }
    v24 = 58;
    goto LABEL_47;
  }
  v26 = *((_QWORD *)DeviceExtension + 8);
  if ( *(_BYTE *)(v26 + 5) == 8 && *(_BYTE *)(v26 + 7) == 80 && !*((_DWORD *)DeviceExtension + 30) )
    *((_DWORD *)DeviceExtension + 30) = 1;
  if ( *((_DWORD *)DeviceExtension + 30) != 1 )
    *((_DWORD *)DeviceExtension + 33) &= ~0x80u;
  Status = USBSTOR_GetPipes(DeviceObject);
  if ( Status < 0 )
    goto LABEL_23;
  if ( (unsigned __int8)USBSTOR_IsDeviceAsyncCapable(DeviceExtension) )
  {
    if ( !*((_QWORD *)DeviceExtension + 47) )
    {
      v36 = IoAllocateWorkItem(DeviceObject);
      *((_QWORD *)DeviceExtension + 47) = v36;
      if ( !v36 )
      {
        Status = -1073741670;
        goto LABEL_23;
      }
    }
  }
  if ( ((unsigned __int8)USBSTOR_IsDeviceAsyncCapable(DeviceExtension)
     || (*((_DWORD *)DeviceExtension + 33) & 0x800) != 0)
    && !*((_QWORD *)DeviceExtension + 48) )
  {
    v33 = IoAllocateWorkItem(DeviceObject);
    *((_QWORD *)DeviceExtension + 48) = v33;
    if ( !v33 )
    {
      Status = -1073741670;
      goto LABEL_23;
    }
  }
  v27 = (_WORD *)*((_QWORD *)DeviceExtension + 6);
  if ( v27 && v27[4] == 1403 && !v27[5] && v27[6] < 0x128u )
    *((_DWORD *)DeviceExtension + 33) |= 1u;
  if ( *((char **)DeviceExtension + 4) == DeviceExtension + 32 )
  {
    Status = USBSTOR_EnumerateChildren(DeviceObject);
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
      goto LABEL_23;
    }
  }
  if ( (int)USBSTOR_GetBusInterface(DeviceObject, &v53) >= 0 )
  {
    DeviceExtension[1813] = v57(*((_QWORD *)&v53 + 1));
    (*((void (__fastcall **)(_QWORD))&v54 + 1))(*((_QWORD *)&v53 + 1));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v37 = "TRUE";
      if ( !DeviceExtension[1813] )
        v37 = "FALSE";
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 60, v28, v37);
    }
  }
  else
  {
    DeviceExtension[1813] = 0;
  }
  if ( USBD_CreateHandle(DeviceObject, *((PDEVICE_OBJECT *)DeviceExtension + 3), v28, v29, &USBDHandle) >= 0 )
  {
    v34 = USBDHandle;
    if ( USBD_QueryUsbCapability(USBDHandle, v30, v31, v32, Irpa) >= 0 )
      DeviceExtension[1814] = 1;
    *((_BYTE *)v34 + 225) = 1;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v34 + 55, 0xFFFFFFFF) <= 1 )
    {
      if ( *((_BYTE *)v34 + 225) )
      {
        v35 = (void (__fastcall *)(_QWORD))*((_QWORD *)v34 + 14);
        if ( v35 )
          v35(*((_QWORD *)v34 + 6));
        ExFreePoolWithTag(v34, *((_DWORD *)v34 + 16));
      }
      else if ( g_EnableDbgPrints )
      {
        DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n", v34);
      }
    }
  }
  if ( DeviceExtension[1813] || DeviceExtension[1814] )
  {
    v38 = *((_DWORD *)DeviceExtension + 34);
    if ( v38 < 0x10001 )
    {
      if ( !DeviceExtension[1814]
        || (*((_DWORD *)DeviceExtension + 33) & 0x200) != 0
        || DeviceExtension[1961] && !DeviceExtension[1864] )
      {
        if ( (*((_DWORD *)DeviceExtension + 33) & 8) != 0 )
          *((_DWORD *)DeviceExtension + 454) = 0x20000;
      }
      else
      {
        *((_DWORD *)DeviceExtension + 454) = 0x80000;
      }
    }
    else
    {
      *((_DWORD *)DeviceExtension + 454) = v38;
    }
    *((_DWORD *)DeviceExtension + 455) = (*((_DWORD *)DeviceExtension + 454) >> 12)
                                       + ((*((_DWORD *)DeviceExtension + 454) & 0xFFF) != 0)
                                       + 1;
  }
  if ( (unsigned __int8)USBSTOR_IsDeviceAsyncCapable(DeviceExtension) )
    USBSTOR_QueueAsyncNotification(DeviceObject, DeviceExtension);
  if ( !DeviceExtension[1932] )
  {
    Status = USBSTOR_WmiRegister(DeviceExtension);
    if ( Status < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
      Status = 0;
    }
    goto LABEL_23;
  }
LABEL_24:
  if ( KeGetCurrentIrql() < 2u )
  {
    v19 = KfRaiseIrql(2u);
    v2 = 1;
  }
  else
  {
    v19 = 0;
  }
  if ( DeviceObject->DeviceQueue.Busy )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 1347310409;
      *(_QWORD *)(qword_14001A190 + 8) = DeviceObject;
      *(_QWORD *)(qword_14001A190 + 16) = 0;
      *(_QWORD *)(qword_14001A190 + 24) = 0;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v20 = qword_14001A198 - 32;
      else
        v20 = qword_14001A190 - 32;
      qword_14001A190 = v20;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    IoStartNextPacket(DeviceObject, 1u);
  }
  if ( v2 )
    KeLowerIrql(v19);
  DeviceExtension[1932] = 0;
LABEL_35:
  p_IoStatus->Status = Status;
  IofCompleteRequest(Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1953657971;
    *(_QWORD *)(qword_14001A190 + 8) = Status;
    *(_QWORD *)(qword_14001A190 + 16) = 0;
    *(_QWORD *)(qword_14001A190 + 24) = 0;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v21 = qword_14001A198 - 32;
    else
      v21 = qword_14001A190 - 32;
    qword_14001A190 = v21;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140008590  mov     [rsp-8+arg_10], rbx
0x140008595  push    rbp
0x140008596  push    rsi
0x140008597  push    rdi
0x140008598  push    r12
0x14000859a  push    r13
0x14000859c  push    r14
0x14000859e  push    r15
0x1400085a0  lea     rbp, [rsp-30h]
0x1400085a5  sub     rsp, 130h
0x1400085ac  xorps   xmm0, xmm0
0x1400085af  xor     eax, eax
0x1400085b1  xor     r12d, r12d
0x1400085b4  mov     [rbp+60h+var_40], rax
0x1400085b8  mov     [rbp+60h+USBDHandle], r12
0x1400085bc  mov     r14, rdx
0x1400085bf  mov     rsi, rcx
0x1400085c2  movups  [rbp+60h+var_80], xmm0
0x1400085c6  movups  [rbp+60h+var_70], xmm0
0x1400085ca  movups  [rbp+60h+var_60], xmm0
0x1400085ce  movups  [rbp+60h+var_50], xmm0
0x1400085d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400085d9  lea     r13, WPP_GLOBAL_Control
0x1400085e0  cmp     rcx, r13
0x1400085e3  jnz     loc_140008E3B
0x1400085e9  xor     eax, eax
0x1400085eb  xorps   xmm0, xmm0
0x1400085ee  cmp     cs:P, rax
0x1400085f5  movups  xmmword ptr [rsp+160h+LockHandle.LockQueue.Next], xmm0
0x1400085fa  mov     qword ptr [rsp+160h+LockHandle.OldIrql], rax
0x1400085ff  jz      short loc_140008677
0x140008601  lea     rdx, [rsp+160h+LockHandle]; LockHandle
0x140008606  lea     rcx, SpinLock; SpinLock
0x14000860d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140008614  nop     dword ptr [rax+rax+00h]
0x140008619  mov     rax, cs:qword_14001A190
0x140008620  mov     dword ptr [rax], 54525453h
0x140008626  mov     rax, cs:qword_14001A190
0x14000862d  mov     [rax+8], rsi
0x140008631  mov     rax, cs:qword_14001A190
0x140008638  mov     [rax+10h], r14
0x14000863c  mov     rax, cs:qword_14001A190
0x140008643  mov     [rax+18h], r12
0x140008647  mov     rax, cs:qword_14001A190
0x14000864e  cmp     rax, cs:P
0x140008655  jbe     loc_140008B48
0x14000865b  sub     rax, 20h ; ' '
0x14000865f  lea     rcx, [rsp+160h+LockHandle]; LockHandle
0x140008664  mov     cs:qword_14001A190, rax
0x14000866b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140008672  nop     dword ptr [rax+rax+00h]
0x140008677  mov     rbx, [rsi+40h]
0x14000867b  mov     rdx, r14; Irp
0x14000867e  mov     rcx, [rbx+18h]; DeviceObject
0x140008682  mov     [rbx+749h], r12b
0x140008689  call    cs:__imp_IoForwardIrpSynchronously
0x140008690  nop     dword ptr [rax+rax+00h]
0x140008695  lea     r15, [r14+30h]
0x140008699  test    al, al
0x14000869b  jz      loc_140008AEF
0x1400086a1  mov     edi, [r15]
0x1400086a4  test    edi, edi
0x1400086a6  js      loc_140008AF4
0x1400086ac  xorps   xmm0, xmm0
0x1400086af  mov     [rsp+160h+var_110], 1
0x1400086b8  lea     rax, [rbx+74Ch]
0x1400086bf  mov     [rsp+160h+var_FC], r12
0x1400086c4  lea     rcx, [rbx+750h]
0x1400086cb  mov     [rax], r12d
0x1400086ce  mov     [rcx], r12d
0x1400086d1  lea     r11, aDisallowlegacy; "DisallowLegacyDiskDevices"
0x1400086d8  mov     [rsp+160h+var_108], rax
0x1400086dd  lea     r10, aRoothubconnect; "RootHubConnectedEnStorDevices"
0x1400086e4  mov     [rbp+60h+var_E0], rcx
0x1400086e8  xor     eax, eax
0x1400086ea  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x1400086ee  mov     rcx, r12
0x1400086f1  mov     [rsp+160h+var_F4], r12
0x1400086f6  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x1400086fa  mov     [rsp+160h+var_EC], r12d
0x1400086ff  mov     r8d, r12d
0x140008702  mov     [rsp+160h+var_E8], 2
0x14000870b  mov     rdx, r12
0x14000870e  mov     [rbp+60h+var_D4], r12
0x140008712  mov     [rbp+60h+var_CC], r12
0x140008716  mov     [rbp+60h+var_C4], r12d
0x14000871a  mov     [rsp+160h+var_100], 4
0x140008722  mov     [rbp+60h+var_D8], 4
0x140008729  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x14000872d  mov     [rbp+60h+KeyHandle], r12
0x140008731  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x140008735  mov     r9d, dword ptr [rsp+rcx+160h+var_110]
0x14000873a  sub     r9d, 1
0x14000873e  jnz     loc_140008E6A
0x140008744  mov     [rsp+rcx+160h+var_FC+4], r10
0x140008749  mov     dword ptr [rsp+rcx+160h+var_F4+4], 4000004h
0x140008751  inc     rdx
0x140008754  add     rcx, 28h ; '('
0x140008758  cmp     rdx, 2
0x14000875c  jnz     short loc_140008735
0x14000875e  test    r8d, r8d
0x140008761  js      loc_1400088C3
0x140008767  mov     edx, 0A8h
0x14000876c  mov     ecx, 100h
0x140008771  mov     r8d, 53414D55h
0x140008777  call    cs:__imp_ExAllocatePool2
0x14000877e  nop     dword ptr [rax+rax+00h]
0x140008783  mov     r13, rax
0x140008786  test    rax, rax
0x140008789  jz      loc_1400088BC
0x14000878f  lea     rdx, SourceString; "\\Registry\\Machine\\Software\\Policies"...
0x140008796  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x14000879a  call    cs:__imp_RtlInitUnicodeString
0x1400087a1  nop     dword ptr [rax+rax+00h]
0x1400087a6  lea     rax, [rbp+60h+DestinationString]
0x1400087aa  mov     qword ptr [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x1400087b2  xorps   xmm0, xmm0
0x1400087b5  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x1400087b9  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x1400087bd  mov     qword ptr [rbp+60h+ObjectAttributes.Attributes], 240h
0x1400087c5  mov     edx, 20019h; DesiredAccess
0x1400087ca  mov     [rbp+60h+ObjectAttributes.RootDirectory], r12
0x1400087ce  lea     rcx, [rbp+60h+KeyHandle]; KeyHandle
0x1400087d2  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400087d7  call    cs:__imp_ZwOpenKey
0x1400087de  nop     dword ptr [rax+rax+00h]
0x1400087e3  test    eax, eax
0x1400087e5  js      loc_1400088AB
0x1400087eb  mov     rax, [rsp+160h+var_FC+4]
0x1400087f0  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1400087f7  mov     [r13+10h], rax
0x1400087fb  lea     rcx, [rsp+160h+LockHandle]; DestinationString
0x140008800  mov     rax, [rsp+160h+var_108]
0x140008805  xorps   xmm0, xmm0
0x140008808  mov     [r13+18h], rax
0x14000880c  mov     [r13+28h], rax
0x140008810  mov     eax, [rsp+160h+var_100]
0x140008814  mov     [r13+30h], eax
0x140008818  mov     eax, dword ptr [rsp+160h+var_F4+4]
0x14000881c  mov     [r13+20h], eax
0x140008820  mov     rax, [rbp+60h+var_D4+4]
0x140008824  mov     [r13+48h], rax
0x140008828  mov     rax, [rbp+60h+var_E0]
0x14000882c  mov     [r13+50h], rax
0x140008830  mov     [r13+60h], rax
0x140008834  mov     eax, [rbp+60h+var_D8]
0x140008837  mov     [r13+68h], eax
0x14000883b  mov     eax, dword ptr [rbp+60h+var_CC+4]
0x14000883e  mov     [r13+58h], eax
0x140008842  mov     dword ptr [r13+8], 120h
0x14000884a  mov     dword ptr [r13+40h], 120h
0x140008852  mov     rdi, [rbp+60h+KeyHandle]
0x140008856  movups  xmmword ptr [rsp+160h+LockHandle.LockQueue.Next], xmm0
0x14000885b  call    cs:__imp_RtlInitUnicodeString
0x140008862  nop     dword ptr [rax+rax+00h]
0x140008867  lea     rcx, [rsp+160h+LockHandle]; SystemRoutineName
0x14000886c  call    cs:__imp_MmGetSystemRoutineAddress
0x140008873  nop     dword ptr [rax+rax+00h]
0x140008878  mov     r8, r13
0x14000887b  mov     [rsp+160h+Irp], r12
0x140008880  test    rax, rax
0x140008883  mov     rdx, rdi
0x140008886  mov     ecx, 40000000h
0x14000888b  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x140008893  xor     r9d, r9d
0x140008896  call    _guard_dispatch_icall
0x14000889b  mov     rcx, [rbp+60h+KeyHandle]; Handle
0x14000889f  call    cs:__imp_ZwClose
0x1400088a6  nop     dword ptr [rax+rax+00h]
0x1400088ab  xor     edx, edx; Tag
0x1400088ad  mov     rcx, r13; P
0x1400088b0  call    cs:__imp_ExFreePoolWithTag
0x1400088b7  nop     dword ptr [rax+rax+00h]
0x1400088bc  lea     r13, WPP_GLOBAL_Control
0x1400088c3  mov     rcx, rsi
0x1400088c6  call    USBSTOR_IsDeviceConnectedToRootHub
0x1400088cb  mov     [rbx+74Ah], al
0x1400088d1  cmp     [rbx+6A8h], r12
0x1400088d8  jnz     loc_140008B87
0x1400088de  lea     rcx, [rbx+4A8h]; VirtualAddress
0x1400088e5  mov     [rsp+160h+Irp], r12; Irp
0x1400088ea  xor     r9d, r9d; ChargeQuota
0x1400088ed  xor     r8d, r8d; SecondaryBuffer
0x1400088f0  mov     edx, 200h; Length
0x1400088f5  call    cs:__imp_IoAllocateMdl
0x1400088fc  nop     dword ptr [rax+rax+00h]
0x140008901  mov     [rbx+6A8h], rax
0x140008908  test    rax, rax
0x14000890b  jnz     loc_140008B78
0x140008911  mov     edi, 0C000009Ah
0x140008916  cmp     [rbx+78Ch], r12b
0x14000891d  jz      loc_1400089FB
0x140008923  call    cs:__imp_KeGetCurrentIrql
0x14000892a  nop     dword ptr [rax+rax+00h]
0x14000892f  cmp     al, 2
0x140008931  jb      loc_140008AD5
0x140008937  xor     r13b, r13b
0x14000893a  cmp     byte ptr [rsi+0C0h], 0
0x140008941  jz      loc_1400089E8
0x140008947  xor     eax, eax
0x140008949  xorps   xmm0, xmm0
0x14000894c  cmp     cs:P, rax
0x140008953  movups  xmmword ptr [rsp+160h+LockHandle.LockQueue.Next], xmm0
0x140008958  mov     qword ptr [rsp+160h+LockHandle.OldIrql], rax
0x14000895d  jz      short loc_1400089D7
0x14000895f  lea     rdx, [rsp+160h+LockHandle]; LockHandle
0x140008964  lea     rcx, SpinLock; SpinLock
0x14000896b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140008972  nop     dword ptr [rax+rax+00h]
0x140008977  mov     rax, cs:qword_14001A190
0x14000897e  xor     ecx, ecx
0x140008980  mov     dword ptr [rax], 504E5349h
0x140008986  mov     rax, cs:qword_14001A190
0x14000898d  mov     [rax+8], rsi
0x140008991  mov     rax, cs:qword_14001A190
0x140008998  mov     [rax+10h], rcx
0x14000899c  mov     rax, cs:qword_14001A190
0x1400089a3  mov     [rax+18h], rcx
0x1400089a7  mov     rax, cs:qword_14001A190
0x1400089ae  cmp     rax, cs:P
0x1400089b5  jbe     loc_140008B68
0x1400089bb  sub     rax, 20h ; ' '
0x1400089bf  lea     rcx, [rsp+160h+LockHandle]; LockHandle
0x1400089c4  mov     cs:qword_14001A190, rax
0x1400089cb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400089d2  nop     dword ptr [rax+rax+00h]
0x1400089d7  mov     dl, 1; Cancelable
0x1400089d9  mov     rcx, rsi; DeviceObject
0x1400089dc  call    cs:__imp_IoStartNextPacket
0x1400089e3  nop     dword ptr [rax+rax+00h]
0x1400089e8  test    r12b, r12b
0x1400089eb  jnz     loc_140008B33
0x1400089f1  mov     byte ptr [rbx+78Ch], 0
0x1400089f8  xor     r12d, r12d
0x1400089fb  xor     edx, edx; PriorityBoost
0x1400089fd  mov     [r15], edi
0x140008a00  mov     rcx, r14; Irp
0x140008a03  call    cs:__imp_IofCompleteRequest
0x140008a0a  nop     dword ptr [rax+rax+00h]
0x140008a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a16  lea     rax, WPP_GLOBAL_Control
0x140008a1d  cmp     rcx, rax
0x140008a20  jnz     loc_14000906D
0x140008a26  xor     eax, eax
0x140008a28  xorps   xmm0, xmm0
0x140008a2b  cmp     cs:P, rax
0x140008a32  movups  xmmword ptr [rsp+160h+LockHandle.LockQueue.Next], xmm0
0x140008a37  mov     qword ptr [rsp+160h+LockHandle.OldIrql], rax
0x140008a3c  jz      short loc_140008AB7
0x140008a3e  lea     rdx, [rsp+160h+LockHandle]; LockHandle
0x140008a43  lea     rcx, SpinLock; SpinLock
0x140008a4a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140008a51  nop     dword ptr [rax+rax+00h]
0x140008a56  mov     rax, cs:qword_14001A190
0x140008a5d  movsxd  rcx, edi
0x140008a60  mov     dword ptr [rax], 74727473h
0x140008a66  mov     rax, cs:qword_14001A190
0x140008a6d  mov     [rax+8], rcx
0x140008a71  mov     rax, cs:qword_14001A190
0x140008a78  mov     [rax+10h], r12
0x140008a7c  mov     rax, cs:qword_14001A190
0x140008a83  mov     [rax+18h], r12
0x140008a87  mov     rax, cs:qword_14001A190
0x140008a8e  cmp     rax, cs:P
0x140008a95  jbe     loc_140008B58
0x140008a9b  sub     rax, 20h ; ' '
0x140008a9f  lea     rcx, [rsp+160h+LockHandle]; LockHandle
0x140008aa4  mov     cs:qword_14001A190, rax
0x140008aab  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140008ab2  nop     dword ptr [rax+rax+00h]
0x140008ab7  mov     rbx, [rsp+160h+arg_10]
0x140008abf  mov     eax, edi
0x140008ac1  add     rsp, 130h
0x140008ac8  pop     r15
0x140008aca  pop     r14
0x140008acc  pop     r13
0x140008ace  pop     r12
0x140008ad0  pop     rdi
0x140008ad1  pop     rsi
0x140008ad2  pop     rbp
0x140008ad3  retn
0x140008ad5  mov     cl, 2; NewIrql
0x140008ad7  call    cs:__imp_KfRaiseIrql
0x140008ade  nop     dword ptr [rax+rax+00h]
0x140008ae3  movzx   r13d, al
0x140008ae7  mov     r12b, 1
0x140008aea  jmp     loc_14000893A
0x140008aef  mov     edi, 0C0000001h
0x140008af4  mov     rcx, cs:WPP_GLOBAL_Control
0x140008afb  cmp     rcx, r13
0x140008afe  jz      loc_140008916
0x140008b04  mov     eax, [rcx+2Ch]
0x140008b07  test    al, 2
0x140008b09  jz      loc_140008916
0x140008b0f  cmp     byte ptr [rcx+29h], 2
0x140008b13  jb      loc_140008916
0x140008b19  mov     edx, 39h ; '9'
0x140008b1e  mov     rcx, [rcx+18h]
0x140008b22  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140008b29  call    WPP_SF_
  ... truncated ...
```
