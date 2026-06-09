# USBSTOR_CswCompletion

- ea: `0x140003e10`
- end: `0x140004907`
- name: `USBSTOR_CswCompletion`
- size: `2807`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001008`
- `0x140001130`
- `0x140003630`
- `0x140003b90`
- `0x140003e10`
- `0x140004910`
- `0x140007900`
- `0x140007ff0`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`
- `0x140013d40`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140004718`
- `ntoskrnl!KeSetEvent` at `0x140004718`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003e72`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003f26`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003fe8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004069`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400040dc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400041f2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000435c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000442f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000450a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400045c8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004745`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003e72`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003f26`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003fe8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004069`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400040dc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400041f2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000435c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000442f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000450a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400045c8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004745`
- `ntoskrnl!IoStartNextPacket` at `0x14000414a`
- `ntoskrnl!IoStartNextPacket` at `0x14000414a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140004094`
- `ntoskrnl!KeGetCurrentIrql` at `0x140004094`
- `ntoskrnl!KeLowerIrql` at `0x14000432a`
- `ntoskrnl!KeLowerIrql` at `0x14000432a`
- `ntoskrnl!KfRaiseIrql` at `0x1400041a4`
- `ntoskrnl!KfRaiseIrql` at `0x1400041a4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003ecf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003f56`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004045`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004080`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004139`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000424f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400043b9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004494`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004567`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400045df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400046ce`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000479e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003ecf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140003f56`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004045`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004080`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004139`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000424f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400043b9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004494`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004567`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400045df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400046ce`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000479e`

## pseudocode

```c
__int64 __fastcall USBSTOR_CswCompletion(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  __int64 Status; // rdi
  __int64 v5; // rax
  _DWORD *DeviceExtension; // rsi
  void *v7; // r12
  PVOID v8; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  __int64 SecurityContext; // r15
  IO_STATUS_BLOCK *p_IoStatus; // rdx
  char v12; // al
  __int64 v13; // rcx
  unsigned int v14; // edi
  __int64 v15; // rax
  KIRQL v16; // r14
  char v17; // si
  __int64 v18; // rax
  __int64 v20; // rax
  int v21; // eax
  _WORD *v22; // rdi
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rdi
  __int64 v26; // rax
  IO_STATUS_BLOCK *v27; // r9
  _DWORD *v28; // rdi
  unsigned int v29; // eax
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-20h] BYREF
  int v35; // [rsp+80h] [rbp+30h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 161, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    Status = a2->IoStatus.Status;
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1129796419;
    *(_QWORD *)(qword_14001A190 + 8) = a1;
    *(_QWORD *)(qword_14001A190 + 16) = a2;
    *(_QWORD *)(qword_14001A190 + 24) = Status;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v5 = qword_14001A198 - 32;
    else
      v5 = qword_14001A190 - 32;
    qword_14001A190 = v5;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  DeviceExtension = a1->DeviceExtension;
  if ( *DeviceExtension == 558842960 )
  {
    a1 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 2);
    v7 = DeviceExtension;
    DeviceExtension = a1->DeviceExtension;
  }
  else
  {
    v7 = 0;
    if ( *DeviceExtension != 558842950 )
    {
      DeviceExtension = 0;
      a1 = 0;
    }
  }
  v8 = a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(&LockHandle, 0, sizeof(LockHandle));
  SecurityContext = (__int64)CurrentStackLocation->Parameters.Create.SecurityContext;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v8 + 18, &LockHandle);
  *((_DWORD *)v8 + 32) &= ~2u;
  if ( (*((_DWORD *)v8 + 32) & 8) != 0 )
  {
    USBSTOR_LogEntry(827609667, a1, a2, SecurityContext);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v31 = *((_QWORD *)v8 + 146);
    a2->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId = v31;
    a2->IoStatus.Status = -1073741643;
    a2->IoStatus.Information = 0;
    *(_BYTE *)(v31 + 3) = 9;
    USBSTOR_TranslateCDBComplete(a1, (__int64)a2, v31);
    KeSetEvent((PRKEVENT)v8 + 14, 0, 0);
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 829911907;
      *(_QWORD *)(qword_14001A190 + 8) = a1;
      *(_QWORD *)(qword_14001A190 + 16) = a2;
      *(_QWORD *)(qword_14001A190 + 24) = SecurityContext;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v32 = qword_14001A198 - 32;
      else
        v32 = qword_14001A190 - 32;
      qword_14001A190 = v32;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 162, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 3221225494LL;
  }
  else
  {
    *((_QWORD *)v8 + 41) = 0;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    p_IoStatus = &a2->IoStatus;
    v35 = a2->IoStatus.Status;
    if ( v35 < 0 )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( P )
      {
        v25 = (int)DeviceExtension[99];
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_DWORD *)qword_14001A190 = 846689123;
        *(_QWORD *)(qword_14001A190 + 8) = v35;
        *(_QWORD *)(qword_14001A190 + 16) = v25;
        *(_QWORD *)(qword_14001A190 + 24) = 0;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v26 = qword_14001A198 - 32;
        else
          v26 = qword_14001A190 - 32;
        qword_14001A190 = v26;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v27 = &a2->IoStatus;
      }
      else
      {
        v27 = &a2->IoStatus;
      }
      v28 = DeviceExtension + 99;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v28 = DeviceExtension + 99;
        WPP_SF_DD(
          WPP_GLOBAL_Control->AttachedDevice,
          163,
          WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
          (unsigned int)v27->Status,
          DeviceExtension[99]);
      }
      if ( (*v28 & 0xFFFFFFF) == 4 && (v29 = DeviceExtension[428], v29 < 2) )
      {
        DeviceExtension[428] = v29 + 1;
        memset(&LockHandle, 0, sizeof(LockHandle));
        if ( P )
        {
          KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
          *(_DWORD *)qword_14001A190 = 863466339;
          *(_QWORD *)(qword_14001A190 + 8) = a1;
          *(_QWORD *)(qword_14001A190 + 16) = a2;
          *(_QWORD *)(qword_14001A190 + 24) = SecurityContext;
          if ( qword_14001A190 <= (unsigned __int64)P )
            v30 = qword_14001A198 - 32;
          else
            v30 = qword_14001A190 - 32;
          qword_14001A190 = v30;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        USBSTOR_BulkQueueResetPipe(a1, a2);
        return 3221225494LL;
      }
      else
      {
        USBSTOR_LogEntry(880243555, a1, a2, SecurityContext);
        v33 = *((_QWORD *)DeviceExtension + 146);
        CurrentStackLocation->Parameters.WMI.ProviderId = v33;
        a2->IoStatus.Status = -1073741435;
        a2->IoStatus.Information = 0;
        *(_BYTE *)(v33 + 3) = 14;
        USBSTOR_TranslateCDBComplete(a1, (__int64)a2, v33);
        USBSTOR_QueueResetDevice(a1, v7);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 164, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        return 3221225861LL;
      }
    }
    else
    {
      v12 = *((_BYTE *)DeviceExtension + 1204);
      if ( v12 )
      {
        if ( v12 == 1 && SecurityContext == *((_QWORD *)DeviceExtension + 146) )
        {
          memset(&LockHandle, 0, sizeof(LockHandle));
          if ( P )
          {
            KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
            *(_DWORD *)qword_14001A190 = 913797987;
            *(_QWORD *)(qword_14001A190 + 8) = a1;
            *(_QWORD *)(qword_14001A190 + 16) = a2;
            *(_QWORD *)(qword_14001A190 + 24) = SecurityContext;
            if ( qword_14001A190 <= (unsigned __int64)P )
              v20 = qword_14001A198 - 32;
            else
              v20 = qword_14001A190 - 32;
            qword_14001A190 = v20;
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            p_IoStatus = &a2->IoStatus;
          }
          v21 = *(_DWORD *)(SecurityContext + 12);
          *(_WORD *)(SecurityContext + 3) = 516;
          *(_DWORD *)(SecurityContext + 16) = 0;
          if ( (v21 & 0x20) == 0 && *(_BYTE *)(SecurityContext + 11) && *(_QWORD *)(SecurityContext + 32) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 167, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
            }
            v22 = a1->DeviceExtension;
            a2->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId = (ULONG_PTR)(v22 + 860);
            memset(v22 + 860, 0, 0x58u);
            v22[860] = 88;
            *((_BYTE *)v22 + 1730) = 12;
            *((_DWORD *)v22 + 433) = 352;
            *((_DWORD *)v22 + 434) = *(unsigned __int8 *)(*((_QWORD *)v22 + 146) + 11LL);
            *((_QWORD *)v22 + 218) = *(_QWORD *)(*((_QWORD *)v22 + 146) + 32LL);
            *((_BYTE *)v22 + 1792) = 3;
            *((_BYTE *)v22 + 1796) = *(_BYTE *)(*((_QWORD *)v22 + 146) + 11LL);
            USBSTOR_CbwTransfer(a1, a2);
            v14 = -1073741802;
          }
          else
          {
            v14 = -1073741435;
            a2->IoStatus.Information = 0;
            p_IoStatus->Status = -1073741435;
            if ( (*(_DWORD *)(SecurityContext + 12) & 0x800) != 0 )
              *(_BYTE *)(SecurityContext + 3) = 6;
            USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
            memset(&LockHandle, 0, sizeof(LockHandle));
            KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &LockHandle);
            DeviceExtension[32] &= ~0x20u;
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            UsbStorPumpNextRequest(v7);
            UsbStorStartNextPacket(a1);
          }
        }
        else
        {
          memset(&LockHandle, 0, sizeof(LockHandle));
          if ( P )
          {
            KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
            *(_DWORD *)qword_14001A190 = 930575203;
            *(_QWORD *)(qword_14001A190 + 8) = a1;
            *(_QWORD *)(qword_14001A190 + 16) = a2;
            *(_QWORD *)(qword_14001A190 + 24) = SecurityContext;
            if ( qword_14001A190 <= (unsigned __int64)P )
              v23 = qword_14001A198 - 32;
            else
              v23 = qword_14001A190 - 32;
            qword_14001A190 = v23;
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            p_IoStatus = &a2->IoStatus;
          }
          v24 = *((_QWORD *)DeviceExtension + 146);
          v14 = -1073741435;
          CurrentStackLocation->Parameters.WMI.ProviderId = v24;
          p_IoStatus->Status = -1073741435;
          a2->IoStatus.Information = 0;
          *(_BYTE *)(v24 + 3) = 14;
          USBSTOR_TranslateCDBComplete(a1, (__int64)a2, v24);
          USBSTOR_QueueResetDevice(a1, v7);
        }
      }
      else
      {
        v13 = *((_QWORD *)DeviceExtension + 146);
        if ( SecurityContext != v13 )
        {
          *(_BYTE *)(v13 + 11) = *(_BYTE *)(SecurityContext + 16);
          SecurityContext = *((_QWORD *)DeviceExtension + 146);
          CurrentStackLocation->Parameters.WMI.ProviderId = SecurityContext;
          *(_BYTE *)(SecurityContext + 3) |= 0x80u;
        }
        p_IoStatus->Status = 0;
        v14 = 0;
        USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
        a2->IoStatus.Information = *(unsigned int *)(SecurityContext + 16);
        memset(&LockHandle, 0, sizeof(LockHandle));
        if ( P )
        {
          KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
          *(_DWORD *)qword_14001A190 = 897020771;
          *(_QWORD *)(qword_14001A190 + 8) = a1;
          *(_QWORD *)(qword_14001A190 + 16) = a2;
          *(_QWORD *)(qword_14001A190 + 24) = SecurityContext;
          if ( qword_14001A190 <= (unsigned __int64)P )
            v15 = qword_14001A198 - 32;
          else
            v15 = qword_14001A190 - 32;
          qword_14001A190 = v15;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        memset(&LockHandle, 0, sizeof(LockHandle));
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &LockHandle);
        DeviceExtension[32] &= ~0x20u;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        UsbStorPumpNextRequest(v7);
        if ( KeGetCurrentIrql() < 2u )
        {
          v16 = KfRaiseIrql(2u);
          v17 = 1;
        }
        else
        {
          v16 = 0;
          v17 = 0;
        }
        if ( a1->DeviceQueue.Busy )
        {
          memset(&LockHandle, 0, sizeof(LockHandle));
          if ( P )
          {
            KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
            *(_DWORD *)qword_14001A190 = 1347310409;
            *(_QWORD *)(qword_14001A190 + 8) = a1;
            *(_QWORD *)(qword_14001A190 + 16) = 0;
            *(_QWORD *)(qword_14001A190 + 24) = 0;
            if ( qword_14001A190 <= (unsigned __int64)P )
              v18 = qword_14001A198 - 32;
            else
              v18 = qword_14001A190 - 32;
            qword_14001A190 = v18;
            KeReleaseInStackQueuedSpinLock(&LockHandle);
          }
          IoStartNextPacket(a1, 1u);
        }
        if ( v17 )
          KeLowerIrql(v16);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 166, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      return v14;
    }
  }
}

```

## disassembly

```asm
0x140003e10  mov     [rsp-28h+arg_10], rbx
0x140003e15  mov     [rsp-28h+arg_18], rsi
0x140003e1a  push    rbp
0x140003e1b  push    rdi
0x140003e1c  push    r13
0x140003e1e  push    r14
0x140003e20  push    r15
0x140003e22  mov     rbp, rsp
0x140003e25  sub     rsp, 50h
0x140003e29  mov     r14, rdx
0x140003e2c  mov     rbx, rcx
0x140003e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e36  lea     rax, WPP_GLOBAL_Control
0x140003e3d  cmp     rcx, rax
0x140003e40  jz      short loc_140003E4D
0x140003e42  mov     eax, [rcx+2Ch]
0x140003e45  test    al, 1
0x140003e47  jnz     loc_1400047D4
0x140003e4d  xor     eax, eax
0x140003e4f  xorps   xmm0, xmm0
0x140003e52  cmp     cs:P, rax
0x140003e59  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140003e5d  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140003e61  jz      short loc_140003EDB
0x140003e63  movsxd  rdi, dword ptr [r14+30h]
0x140003e67  lea     rdx, [rbp+LockHandle]; LockHandle
0x140003e6b  lea     rcx, SpinLock; SpinLock
0x140003e72  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003e79  nop     dword ptr [rax+rax+00h]
0x140003e7e  mov     rax, cs:qword_14001A190
0x140003e85  mov     dword ptr [rax], 43575343h
0x140003e8b  mov     rax, cs:qword_14001A190
0x140003e92  mov     [rax+8], rbx
0x140003e96  mov     rax, cs:qword_14001A190
0x140003e9d  mov     [rax+10h], r14
0x140003ea1  mov     rax, cs:qword_14001A190
0x140003ea8  mov     [rax+18h], rdi
0x140003eac  mov     rax, cs:qword_14001A190
0x140003eb3  cmp     rax, cs:P
0x140003eba  jbe     loc_140004647
0x140003ec0  sub     rax, 20h ; ' '
0x140003ec4  lea     rcx, [rbp+LockHandle]; LockHandle
0x140003ec8  mov     cs:qword_14001A190, rax
0x140003ecf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003ed6  nop     dword ptr [rax+rax+00h]
0x140003edb  mov     rsi, [rbx+40h]
0x140003edf  mov     [rsp+50h+arg_8], r12
0x140003ee7  mov     eax, [rsi]
0x140003ee9  cmp     eax, 214F4450h
0x140003eee  jnz     loc_1400047F8
0x140003ef4  mov     rbx, [rsi+10h]
0x140003ef8  mov     r12, rsi
0x140003efb  mov     rsi, [rbx+40h]
0x140003eff  mov     rdi, [rbx+40h]
0x140003f03  lea     rdx, [rbp+LockHandle]; LockHandle
0x140003f07  mov     r13, [r14+0B8h]
0x140003f0e  xorps   xmm0, xmm0
0x140003f11  xor     eax, eax
0x140003f13  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140003f17  lea     rcx, [rdi+90h]; SpinLock
0x140003f1e  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140003f22  mov     r15, [r13+8]
0x140003f26  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003f2d  nop     dword ptr [rax+rax+00h]
0x140003f32  and     dword ptr [rdi+80h], 0FFFFFFFDh
0x140003f39  mov     eax, [rdi+80h]
0x140003f3f  test    al, 8
0x140003f41  jnz     loc_1400046B7
0x140003f47  lea     rcx, [rbp+LockHandle]; LockHandle
0x140003f4b  mov     qword ptr [rdi+148h], 0
0x140003f56  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140003f5d  nop     dword ptr [rax+rax+00h]
0x140003f62  mov     eax, [r14+30h]
0x140003f66  lea     rdx, [r14+30h]
0x140003f6a  mov     [rbp+arg_0], eax
0x140003f6d  test    eax, eax
0x140003f6f  js      loc_140004403
0x140003f75  movzx   eax, byte ptr [rsi+4B4h]
0x140003f7c  test    al, al
0x140003f7e  jnz     loc_1400041BC
0x140003f84  mov     rcx, [rsi+490h]
0x140003f8b  cmp     r15, rcx
0x140003f8e  jz      short loc_140003FA8
0x140003f90  movzx   eax, byte ptr [r15+10h]
0x140003f95  mov     [rcx+0Bh], al
0x140003f98  mov     r15, [rsi+490h]
0x140003f9f  mov     [r13+8], r15
0x140003fa3  or      byte ptr [r15+3], 80h
0x140003fa8  xor     r13d, r13d
0x140003fab  mov     r8, r15
0x140003fae  mov     [rdx], r13d
0x140003fb1  mov     rcx, rbx; Object
0x140003fb4  mov     rdx, r14
0x140003fb7  mov     edi, r13d
0x140003fba  call    USBSTOR_TranslateCDBComplete
0x140003fbf  mov     eax, [r15+10h]
0x140003fc3  xorps   xmm0, xmm0
0x140003fc6  mov     [r14+38h], rax
0x140003fca  xor     eax, eax
0x140003fcc  cmp     cs:P, rax
0x140003fd3  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140003fd7  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140003fdb  jz      short loc_140004051
0x140003fdd  lea     rdx, [rbp+LockHandle]; LockHandle
0x140003fe1  lea     rcx, SpinLock; SpinLock
0x140003fe8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140003fef  nop     dword ptr [rax+rax+00h]
0x140003ff4  mov     rax, cs:qword_14001A190
0x140003ffb  mov     dword ptr [rax], 35777363h
0x140004001  mov     rax, cs:qword_14001A190
0x140004008  mov     [rax+8], rbx
0x14000400c  mov     rax, cs:qword_14001A190
0x140004013  mov     [rax+10h], r14
0x140004017  mov     rax, cs:qword_14001A190
0x14000401e  mov     [rax+18h], r15
0x140004022  mov     rax, cs:qword_14001A190
0x140004029  cmp     rax, cs:P
0x140004030  jbe     loc_140004657
0x140004036  sub     rax, 20h ; ' '
0x14000403a  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000403e  mov     cs:qword_14001A190, rax
0x140004045  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000404c  nop     dword ptr [rax+rax+00h]
0x140004051  xorps   xmm0, xmm0
0x140004054  lea     rcx, [rsi+90h]; SpinLock
0x14000405b  xor     eax, eax
0x14000405d  lea     rdx, [rbp+LockHandle]; LockHandle
0x140004061  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140004065  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140004069  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140004070  nop     dword ptr [rax+rax+00h]
0x140004075  and     dword ptr [rsi+80h], 0FFFFFFDFh
0x14000407c  lea     rcx, [rbp+LockHandle]; LockHandle
0x140004080  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140004087  nop     dword ptr [rax+rax+00h]
0x14000408c  mov     rcx, r12
0x14000408f  call    UsbStorPumpNextRequest
0x140004094  call    cs:__imp_KeGetCurrentIrql
0x14000409b  nop     dword ptr [rax+rax+00h]
0x1400040a0  cmp     al, 2
0x1400040a2  jb      loc_1400041A2
0x1400040a8  xor     r14b, r14b
0x1400040ab  xor     sil, sil
0x1400040ae  cmp     [rbx+0C0h], dil
0x1400040b5  jz      loc_140004156
0x1400040bb  xor     eax, eax
0x1400040bd  xorps   xmm0, xmm0
0x1400040c0  cmp     cs:P, rax
0x1400040c7  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400040cb  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400040cf  jz      short loc_140004145
0x1400040d1  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400040d5  lea     rcx, SpinLock; SpinLock
0x1400040dc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400040e3  nop     dword ptr [rax+rax+00h]
0x1400040e8  mov     rax, cs:qword_14001A190
0x1400040ef  mov     dword ptr [rax], 504E5349h
0x1400040f5  mov     rax, cs:qword_14001A190
0x1400040fc  mov     [rax+8], rbx
0x140004100  mov     rax, cs:qword_14001A190
0x140004107  mov     [rax+10h], r13
0x14000410b  mov     rax, cs:qword_14001A190
0x140004112  mov     [rax+18h], r13
0x140004116  mov     rax, cs:qword_14001A190
0x14000411d  cmp     rax, cs:P
0x140004124  jbe     loc_140004667
0x14000412a  sub     rax, 20h ; ' '
0x14000412e  lea     rcx, [rbp+LockHandle]; LockHandle
0x140004132  mov     cs:qword_14001A190, rax
0x140004139  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140004140  nop     dword ptr [rax+rax+00h]
0x140004145  mov     dl, 1; Cancelable
0x140004147  mov     rcx, rbx; DeviceObject
0x14000414a  call    cs:__imp_IoStartNextPacket
0x140004151  nop     dword ptr [rax+rax+00h]
0x140004156  test    sil, sil
0x140004159  jnz     loc_140004326
0x14000415f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004166  lea     rax, WPP_GLOBAL_Control
0x14000416d  cmp     rcx, rax
0x140004170  jz      short loc_14000417E
0x140004172  mov     edx, [rcx+2Ch]
0x140004175  test    dl, 1
0x140004178  jnz     loc_1400048E0
0x14000417e  mov     eax, edi
0x140004180  mov     r12, [rsp+50h+arg_8]
0x140004188  lea     r11, [rsp+50h+var_s0]
0x14000418d  mov     rbx, [r11+40h]
0x140004191  mov     rsi, [r11+48h]
0x140004195  mov     rsp, r11
0x140004198  pop     r15
0x14000419a  pop     r14
0x14000419c  pop     r13
0x14000419e  pop     rdi
0x14000419f  pop     rbp
0x1400041a0  retn
0x1400041a2  mov     cl, 2; NewIrql
0x1400041a4  call    cs:__imp_KfRaiseIrql
0x1400041ab  nop     dword ptr [rax+rax+00h]
0x1400041b0  movzx   r14d, al
0x1400041b4  mov     sil, 1
0x1400041b7  jmp     loc_1400040AE
0x1400041bc  cmp     al, 1
0x1400041be  jnz     loc_14000433B
0x1400041c4  cmp     r15, [rsi+490h]
0x1400041cb  jnz     loc_14000433B
0x1400041d1  xor     eax, eax
0x1400041d3  xorps   xmm0, xmm0
0x1400041d6  cmp     cs:P, rax
0x1400041dd  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400041e1  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400041e5  jz      short loc_14000425F
0x1400041e7  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400041eb  lea     rcx, SpinLock; SpinLock
0x1400041f2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400041f9  nop     dword ptr [rax+rax+00h]
0x1400041fe  mov     rax, cs:qword_14001A190
0x140004205  mov     dword ptr [rax], 36777363h
0x14000420b  mov     rax, cs:qword_14001A190
0x140004212  mov     [rax+8], rbx
0x140004216  mov     rax, cs:qword_14001A190
0x14000421d  mov     [rax+10h], r14
0x140004221  mov     rax, cs:qword_14001A190
0x140004228  mov     [rax+18h], r15
0x14000422c  mov     rax, cs:qword_14001A190
0x140004233  cmp     rax, cs:P
0x14000423a  jbe     loc_140004677
0x140004240  sub     rax, 20h ; ' '
0x140004244  lea     rcx, [rbp+LockHandle]; LockHandle
0x140004248  mov     cs:qword_14001A190, rax
0x14000424f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140004256  nop     dword ptr [rax+rax+00h]
0x14000425b  lea     rdx, [r14+30h]
0x14000425f  mov     eax, [r15+0Ch]
0x140004263  xor     ecx, ecx
0x140004265  mov     word ptr [r15+3], 204h
0x14000426c  mov     [r15+10h], ecx
0x140004270  test    al, 20h
0x140004272  jnz     loc_140004588
0x140004278  cmp     [r15+0Bh], cl
0x14000427c  jz      loc_140004588
0x140004282  cmp     [r15+20h], rcx
0x140004286  jz      loc_140004588
0x14000428c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004293  lea     rax, WPP_GLOBAL_Control
0x14000429a  cmp     rcx, rax
0x14000429d  jz      short loc_1400042AA
0x14000429f  mov     eax, [rcx+2Ch]
0x1400042a2  test    al, 1
0x1400042a4  jnz     loc_1400048BC
0x1400042aa  mov     rdi, [rbx+40h]
0x1400042ae  mov     r15d, 58h ; 'X'
0x1400042b4  mov     rax, [r14+0B8h]
0x1400042bb  mov     r8d, r15d; Size
0x1400042be  xor     edx, edx; Val
0x1400042c0  lea     rsi, [rdi+6B8h]
0x1400042c7  mov     rcx, rsi; void *
0x1400042ca  mov     [rax+8], rsi
0x1400042ce  call    memset
0x1400042d3  mov     [rsi], r15w
0x1400042d7  mov     rdx, r14; Irp
0x1400042da  mov     byte ptr [rsi+0Ah], 0Ch
0x1400042de  mov     dword ptr [rsi+0Ch], 160h
0x1400042e5  mov     rax, [rdi+490h]
0x1400042ec  movzx   ecx, byte ptr [rax+0Bh]
0x1400042f0  mov     [rsi+10h], ecx
0x1400042f3  mov     rax, [rdi+490h]
0x1400042fa  mov     rcx, [rax+20h]
0x1400042fe  mov     [rsi+18h], rcx
0x140004302  mov     byte ptr [rsi+48h], 3
0x140004306  mov     rax, [rdi+490h]
0x14000430d  movzx   ecx, byte ptr [rax+0Bh]
0x140004311  mov     [rsi+4Ch], cl
0x140004314  mov     rcx, rbx; Object
0x140004317  call    USBSTOR_CbwTransfer
0x14000431c  mov     edi, 0C0000016h
0x140004321  jmp     loc_14000415F
0x140004326  movzx   ecx, r14b; NewIrql
0x14000432a  call    cs:__imp_KeLowerIrql
0x140004331  nop     dword ptr [rax+rax+00h]
0x140004336  jmp     loc_14000415F
0x14000433b  xor     eax, eax
0x14000433d  xorps   xmm0, xmm0
0x140004340  cmp     cs:P, rax
0x140004347  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14000434b  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14000434f  jz      short loc_1400043C9
0x140004351  lea     rdx, [rbp+LockHandle]; LockHandle
0x140004355  lea     rcx, SpinLock; SpinLock
0x14000435c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140004363  nop     dword ptr [rax+rax+00h]
0x140004368  mov     rax, cs:qword_14001A190
0x14000436f  mov     dword ptr [rax], 37777363h
0x140004375  mov     rax, cs:qword_14001A190
0x14000437c  mov     [rax+8], rbx
0x140004380  mov     rax, cs:qword_14001A190
0x140004387  mov     [rax+10h], r14
0x14000438b  mov     rax, cs:qword_14001A190
0x140004392  mov     [rax+18h], r15
0x140004396  mov     rax, cs:qword_14001A190
  ... truncated ...
```
