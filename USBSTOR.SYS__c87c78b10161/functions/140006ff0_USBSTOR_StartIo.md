# USBSTOR_StartIo

- ea: `0x140006ff0`
- end: `0x1400078f6`
- name: `USBSTOR_StartIo`
- size: `2310`
- prototype: `__int64 __fastcall(PVOID Object, PIRP Irp)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003630`
- `0x140003b90`
- `0x140005d80`
- `0x140006ff0`
- `0x140007900`
- `0x140007ff0`
- `0x14000d7e4`
- `0x14000e3a4`
- `0x14000e8bc`
- `0x140010594`
- `0x1400105e8`
- `0x140011ec8`
- `0x140013d40`

## import_xrefs

- `ntoskrnl!PoCallDriver` at `0x140007483`
- `ntoskrnl!PoCallDriver` at `0x140007483`
- `ntoskrnl!KeSetEvent` at `0x1400073e0`
- `ntoskrnl!KeSetEvent` at `0x1400073e0`
- `ntoskrnl!IofCompleteRequest` at `0x140007534`
- `ntoskrnl!IofCompleteRequest` at `0x1400076f7`
- `ntoskrnl!IofCompleteRequest` at `0x140007534`
- `ntoskrnl!IofCompleteRequest` at `0x1400076f7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007038`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007244`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000763f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007038`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140007244`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000763f`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400070f6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400070f6`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140007117`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400074db`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140007117`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400074db`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140007139`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400074b0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140007139`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400074b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007168`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400074cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007612`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007168`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400074cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007612`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400071aa`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400071aa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007095`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400072a1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000769c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140007095`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400072a1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000769c`
- `HAL!KeQueryPerformanceCounter` at `0x1400078ac`
- `HAL!KeQueryPerformanceCounter` at `0x1400078ac`

## pseudocode

```c
void __fastcall USBSTOR_StartIo(struct _DEVICE_OBJECT *Object, PIRP Irp)
{
  char v2; // r12
  __int64 v5; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int *DeviceExtension; // rdi
  PUNICODE_STRING FileName; // r13
  PIO_SECURITY_CONTEXT v9; // r14
  int v10; // eax
  unsigned int v11; // eax
  __int64 FullCreateOptions; // rax
  char *v13; // r15
  __int64 v14; // rax
  __int64 v15; // rax
  char SecurityQos; // al
  char v17; // dl
  char v18; // r8
  char v19; // al
  struct _KEVENT *v20; // rcx
  struct _IO_STACK_LOCATION *v21; // rax
  struct _IO_STACK_LOCATION *v22; // rdx
  void *v23; // rax
  int v24; // r15d
  PIO_SECURITY_CONTEXT SecurityContext; // rdx
  __int64 v26; // rax
  char v27; // cl
  char v28; // r8
  char v29; // al
  struct _KLOCK_QUEUE_HANDLE v30; // [rsp+30h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-18h] BYREF
  KIRQL Irql; // [rsp+90h] [rbp+30h] BYREF

  v2 = 0;
  Irql = 0;
  memset(&v30, 0, sizeof(v30));
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1330205779;
    *(_QWORD *)(qword_14001A190 + 8) = Object;
    *(_QWORD *)(qword_14001A190 + 16) = Irp;
    *(_QWORD *)(qword_14001A190 + 24) = 0;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v5 = qword_14001A198 - 32;
    else
      v5 = qword_14001A190 - 32;
    qword_14001A190 = v5;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids, Object, Irp);
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = (int *)Object->DeviceExtension;
  if ( CurrentStackLocation->MajorFunction == 22 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids, Object, Irp);
    }
    USBSTOR_LogEntry(1128550470, Object, Irp, (int)CurrentStackLocation->Parameters.Read.ByteOffset.LowPart);
    if ( (Object->Flags & 0x2000) == 0 )
    {
      v21 = Irp->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v21[-1].MajorFunction = *(_OWORD *)&v21->MajorFunction;
      *(_OWORD *)&v21[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v21->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v21[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v21->Parameters.SetQuota + 6);
      v21[-1].FileObject = v21->FileObject;
      v21[-1].Control = 0;
      v22 = Irp->Tail.Overlay.CurrentStackLocation;
      v23 = (void *)DeviceExtension[482];
      v22[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)USBSTOR_FdoSetPowerSxCompletion;
      v22[-1].Context = v23;
      v22[-1].Control = -32;
      PoCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 3), Irp);
      return;
    }
    v20 = (struct _KEVENT *)(DeviceExtension + 42);
LABEL_41:
    KeSetEvent(v20, 0, 0);
    return;
  }
  if ( CurrentStackLocation->MajorFunction == 27 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids, Object, Irp);
    }
    USBSTOR_LogEntry(1347703622, Object, Irp, 0);
    v20 = (struct _KEVENT *)(DeviceExtension + 484);
    goto LABEL_41;
  }
  FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
  IoAcquireCancelSpinLock(&Irql);
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0);
  if ( Irp->Cancel )
  {
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)DeviceExtension + 18, &v30);
    v24 = DeviceExtension[32] & 8;
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&v30);
    IoReleaseCancelSpinLock(Irql);
    USBSTOR_LogEntry(860766531, Object, Irp, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids, Object, Irp);
    }
    Irp->IoStatus.Status = -1073741536;
    Irp->IoStatus.Information = 0;
    SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
    BYTE3(SecurityContext->SecurityQos) = 2;
    USBSTOR_FxPowerReference(DeviceExtension, SecurityContext, 0);
    IofCompleteRequest(Irp, 0);
    if ( !v24 )
    {
      UsbStorPumpNextRequest(FileName);
      UsbStorStartNextPacket(Object);
    }
  }
  else
  {
    IoReleaseCancelSpinLock(Irql);
    v9 = CurrentStackLocation->Parameters.Create.SecurityContext;
    *((_QWORD *)DeviceExtension + 146) = v9;
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)DeviceExtension + 18, &v30);
    v10 = DeviceExtension[32];
    if ( (v10 & 0x10) != 0 )
    {
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&v30);
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( P )
      {
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_DWORD *)qword_14001A190 = 1685023091;
        *(_QWORD *)(qword_14001A190 + 8) = Object;
        *(_QWORD *)(qword_14001A190 + 16) = Irp;
        *(_QWORD *)(qword_14001A190 + 24) = 0;
        if ( qword_14001A190 <= (unsigned __int64)P )
          v26 = qword_14001A198 - 32;
        else
          v26 = qword_14001A190 - 32;
        qword_14001A190 = v26;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids, Object, Irp);
      }
      BYTE3(v9->SecurityQos) = 8;
      v9->DesiredAccess = 0;
      Irp->IoStatus.Status = -1073741667;
      Irp->IoStatus.Information = 0;
      if ( (HIDWORD(v9->AccessState) & 0x80010) != 0 && (unsigned __int8)UsbQueueIsBypassIrp(Irp, &FileName[23]) )
      {
        UsbQueueClearBypassIrp(&FileName[23]);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        USBSTOR_LogEntry(826429763, Object, &FileName[23], SHIDWORD(FileName[41].Buffer));
      }
      USBSTOR_FxPowerReference(DeviceExtension, v9, 0);
      IofCompleteRequest(Irp, 0);
      UsbStorPumpNextRequest(FileName);
      UsbStorStartNextPacket(Object);
    }
    else
    {
      v11 = v10 & 0xFFFFFFBF;
      DeviceExtension[32] = v11;
      if ( (v11 & 4) != 0 )
      {
        v2 = 1;
        DeviceExtension[32] = v11 & 0xFFFFFFFB;
      }
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&v30);
      FullCreateOptions = v9->FullCreateOptions;
      if ( (_DWORD)FullCreateOptions )
      {
        if ( LOBYTE(v9[3].SecurityQos) == 27 && (unsigned int)FullCreateOptions > 0x3C )
          FullCreateOptions = (unsigned int)(FullCreateOptions - 19);
        KeSetCoalescableTimer(
          (PKTIMER)DeviceExtension + 3,
          (LARGE_INTEGER)(-10000000 * FullCreateOptions),
          0,
          0x1F4u,
          (PKDPC)DeviceExtension + 4);
      }
      *((_QWORD *)DeviceExtension + 40) = MEMORY[0xFFFFF78000000014];
      v13 = (char *)Object->DeviceExtension;
      if ( LOBYTE(v9[3].SecurityQos) == 26 && v9->DesiredAccess >= 4 && v13[1824] )
        HIDWORD(v9->AccessState) |= 0x1000000u;
      if ( *(_BYTE *)(*((_QWORD *)v13 + 8) + 6LL) != 6 )
      {
        *(_OWORD *)(v13 + 1176) = *(_OWORD *)&v9[3].SecurityQos;
        v15 = BYTE2(v9->AccessState);
        if ( (unsigned __int8)v15 >= 0x10u )
        {
          if ( (unsigned __int8)v15 > 0x10u )
            LOBYTE(v15) = 16;
        }
        else
        {
          memset((char *)&v9[3] + v15, 0, 16 - v15);
          LOBYTE(v15) = 12;
        }
        BYTE2(v9->AccessState) = v15;
        SecurityQos = (char)v9[3].SecurityQos;
        if ( SecurityQos )
        {
          if ( SecurityQos == 21 )
          {
            v27 = BYTE1(v9[3].SecurityQos);
            v28 = BYTE4(v9[3].SecurityQos);
            *(_OWORD *)&v9[3].SecurityQos = 0;
            v29 = BYTE1(v9[3].SecurityQos);
            LOBYTE(v9[3].SecurityQos) = 85;
            LOBYTE(v9[3].AccessState) = v28;
            BYTE1(v9[3].SecurityQos) = v29 ^ (v27 ^ v29) & 1 | 0x10;
          }
          else if ( SecurityQos == 26 )
          {
            v17 = BYTE2(v9[3].SecurityQos);
            v18 = BYTE4(v9[3].SecurityQos);
            *(_OWORD *)&v9[3].SecurityQos = 0;
            v19 = BYTE2(v9[3].SecurityQos);
            LOBYTE(v9[3].SecurityQos) = 90;
            BYTE2(v9[3].SecurityQos) = v19 ^ (v17 ^ v19) & 0x3F;
            LOBYTE(v9[3].AccessState) = v18;
          }
        }
        else if ( (*((_DWORD *)v13 + 33) & 4) != 0 )
        {
          *(_OWORD *)&v9[3].SecurityQos = 0;
          BYTE4(v9[3].SecurityQos) |= 1u;
          LOBYTE(v9[3].SecurityQos) = 27;
        }
      }
      if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 && FileName && LOBYTE(FileName[51].Length) )
        FileName[50].Buffer = (PWSTR)KeQueryPerformanceCounter(0).QuadPart;
      if ( DeviceExtension[30] == 1 )
      {
        USBSTOR_CbwTransfer(Object, Irp);
      }
      else if ( !v2 || LOBYTE(v9[3].SecurityQos) == 3 )
      {
        USBSTOR_IssueClientCdb(Object, Irp);
      }
      else
      {
        USBSTOR_IssueRequestSenseCdb(Object, Irp, 1);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 1869182067;
      *(_QWORD *)(qword_14001A190 + 8) = Object;
      *(_QWORD *)(qword_14001A190 + 16) = Irp;
      *(_QWORD *)(qword_14001A190 + 24) = 0;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v14 = qword_14001A198 - 32;
      else
        v14 = qword_14001A190 - 32;
      qword_14001A190 = v14;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
  }
}

```

## disassembly

```asm
0x140006ff0  mov     [rsp-28h+arg_18], rbx
0x140006ff5  push    rbp
0x140006ff6  push    rsi
0x140006ff7  push    rdi
0x140006ff8  push    r12
0x140006ffa  push    r14
0x140006ffc  mov     rbp, rsp
0x140006fff  sub     rsp, 60h
0x140007003  xor     eax, eax
0x140007005  xorps   xmm0, xmm0
0x140007008  xor     r12d, r12d
0x14000700b  mov     qword ptr [rbp+var_30.OldIrql], rax
0x14000700f  cmp     cs:P, rax
0x140007016  mov     rbx, rdx
0x140007019  mov     rsi, rcx
0x14000701c  mov     [rbp+Irql], al
0x14000701f  movups  xmmword ptr [rbp+var_30.LockQueue.Next], xmm0
0x140007023  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140007027  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14000702b  jz      short loc_1400070A1
0x14000702d  lea     rdx, [rbp+LockHandle]; LockHandle
0x140007031  lea     rcx, SpinLock; SpinLock
0x140007038  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000703f  nop     dword ptr [rax+rax+00h]
0x140007044  mov     rax, cs:qword_14001A190
0x14000704b  mov     dword ptr [rax], 4F495453h
0x140007051  mov     rax, cs:qword_14001A190
0x140007058  mov     [rax+8], rsi
0x14000705c  mov     rax, cs:qword_14001A190
0x140007063  mov     [rax+10h], rbx
0x140007067  mov     rax, cs:qword_14001A190
0x14000706e  mov     [rax+18h], r12
0x140007072  mov     rax, cs:qword_14001A190
0x140007079  cmp     rax, cs:P
0x140007080  jbe     loc_140007584
0x140007086  sub     rax, 20h ; ' '
0x14000708a  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000708e  mov     cs:qword_14001A190, rax
0x140007095  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000709c  nop     dword ptr [rax+rax+00h]
0x1400070a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400070a8  lea     rdx, WPP_GLOBAL_Control
0x1400070af  cmp     rcx, rdx
0x1400070b2  jz      short loc_1400070BF
0x1400070b4  mov     eax, [rcx+2Ch]
0x1400070b7  test    al, 1
0x1400070b9  jnz     loc_1400075A4
0x1400070bf  mov     r14, [rbx+0B8h]
0x1400070c6  mov     rdi, [rsi+40h]
0x1400070ca  movzx   eax, byte ptr [r14]
0x1400070ce  cmp     al, 16h
0x1400070d0  jz      loc_1400073F1
0x1400070d6  cmp     al, 1Bh
0x1400070d8  jz      loc_1400073B1
0x1400070de  mov     [rsp+60h+arg_8], r13
0x1400070e6  lea     rcx, [rbp+Irql]; Irql
0x1400070ea  mov     r13, [r14+10h]
0x1400070ee  mov     [rsp+60h+arg_10], r15
0x1400070f6  call    cs:__imp_IoAcquireCancelSpinLock
0x1400070fd  nop     dword ptr [rax+rax+00h]
0x140007102  mov     rax, r12
0x140007105  xchg    rax, [rbx+68h]
0x140007109  cmp     [rbx+44h], r12b
0x14000710d  jnz     loc_1400074A5
0x140007113  movzx   ecx, [rbp+Irql]; Irql
0x140007117  call    cs:__imp_IoReleaseCancelSpinLock
0x14000711e  nop     dword ptr [rax+rax+00h]
0x140007123  mov     r14, [r14+8]
0x140007127  lea     rdx, [rbp+var_30]; LockHandle
0x14000712b  lea     rcx, [rdi+90h]; SpinLock
0x140007132  mov     [rdi+490h], r14
0x140007139  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140007140  nop     dword ptr [rax+rax+00h]
0x140007145  mov     eax, [rdi+80h]
0x14000714b  lea     rcx, [rbp+var_30]; LockHandle
0x14000714f  test    al, 10h
0x140007151  jnz     loc_140007612
0x140007157  and     eax, 0FFFFFFBFh
0x14000715a  mov     [rdi+80h], eax
0x140007160  test    al, 4
0x140007162  jnz     loc_14000784C
0x140007168  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14000716f  nop     dword ptr [rax+rax+00h]
0x140007174  mov     eax, [r14+14h]
0x140007178  test    eax, eax
0x14000717a  jz      short loc_1400071B6
0x14000717c  cmp     byte ptr [r14+48h], 1Bh
0x140007181  jz      loc_140007494
0x140007187  lea     r8, [rdi+100h]
0x14000718e  mov     r9d, 1F4h; TolerableDelay
0x140007194  mov     [rsp+60h+Dpc], r8; Dpc
0x140007199  lea     rcx, [rdi+0C0h]; Timer
0x1400071a0  imul    rdx, rax, 0FFFFFFFFFF676980h; DueTime
0x1400071a7  xor     r8d, r8d; Period
0x1400071aa  call    cs:__imp_KeSetCoalescableTimer
0x1400071b1  nop     dword ptr [rax+rax+00h]
0x1400071b6  mov     rax, ds:0FFFFF78000000014h
0x1400071c0  mov     [rdi+140h], rax
0x1400071c7  cmp     byte ptr [r14+48h], 1Ah
0x1400071cc  mov     r15, [rsi+40h]
0x1400071d0  jz      loc_140007304
0x1400071d6  mov     rax, [r15+40h]
0x1400071da  cmp     byte ptr [rax+6], 6
0x1400071de  jnz     loc_14000732A
0x1400071e4  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x1400071eb  jnz     loc_140007893
0x1400071f1  cmp     dword ptr [rdi+78h], 1
0x1400071f5  jnz     loc_1400078C4
0x1400071fb  mov     rdx, rbx; Irp
0x1400071fe  mov     rcx, rsi; Object
0x140007201  call    USBSTOR_CbwTransfer
0x140007206  mov     r15d, eax
0x140007209  xor     r12d, r12d
0x14000720c  mov     rcx, cs:WPP_GLOBAL_Control
0x140007213  lea     rax, WPP_GLOBAL_Control
0x14000721a  cmp     rcx, rax
0x14000721d  jnz     loc_1400072D2
0x140007223  xor     eax, eax
0x140007225  xorps   xmm0, xmm0
0x140007228  cmp     cs:P, rax
0x14000722f  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x140007233  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x140007237  jz      short loc_1400072AD
0x140007239  lea     rdx, [rbp+LockHandle]; LockHandle
0x14000723d  lea     rcx, SpinLock; SpinLock
0x140007244  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000724b  nop     dword ptr [rax+rax+00h]
0x140007250  mov     rax, cs:qword_14001A190
0x140007257  mov     dword ptr [rax], 6F697473h
0x14000725d  mov     rax, cs:qword_14001A190
0x140007264  mov     [rax+8], rsi
0x140007268  mov     rax, cs:qword_14001A190
0x14000726f  mov     [rax+10h], rbx
0x140007273  mov     rax, cs:qword_14001A190
0x14000727a  mov     [rax+18h], r12
0x14000727e  mov     rax, cs:qword_14001A190
0x140007285  cmp     rax, cs:P
0x14000728c  jbe     loc_140007594
0x140007292  sub     rax, 20h ; ' '
0x140007296  lea     rcx, [rbp+LockHandle]; LockHandle
0x14000729a  mov     cs:qword_14001A190, rax
0x1400072a1  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400072a8  nop     dword ptr [rax+rax+00h]
0x1400072ad  mov     r13, [rsp+60h+arg_8]
0x1400072b5  mov     r15, [rsp+60h+arg_10]
0x1400072bd  mov     rbx, [rsp+60h+arg_18]
0x1400072c5  add     rsp, 60h
0x1400072c9  pop     r14
0x1400072cb  pop     r12
0x1400072cd  pop     rdi
0x1400072ce  pop     rsi
0x1400072cf  pop     rbp
0x1400072d0  retn
0x1400072d2  mov     eax, [rcx+2Ch]
0x1400072d5  test    al, 1
0x1400072d7  jz      loc_140007223
0x1400072dd  cmp     byte ptr [rcx+29h], 4
0x1400072e1  jb      loc_140007223
0x1400072e7  mov     rcx, [rcx+18h]
0x1400072eb  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400072f2  mov     edx, 55h ; 'U'
0x1400072f7  mov     r9d, r15d
0x1400072fa  call    WPP_SF_d
0x1400072ff  jmp     loc_140007223
0x140007304  cmp     dword ptr [r14+10h], 4
0x140007309  jb      loc_1400071D6
0x14000730f  cmp     byte ptr [r15+720h], 0
0x140007317  jz      loc_1400071D6
0x14000731d  or      dword ptr [r14+0Ch], 1000000h
0x140007325  jmp     loc_1400071D6
0x14000732a  movups  xmm0, xmmword ptr [r14+48h]
0x14000732f  movups  xmmword ptr [r15+498h], xmm0
0x140007337  movzx   eax, byte ptr [r14+0Ah]
0x14000733c  cmp     al, 10h
0x14000733e  jnb     loc_140007605
0x140007344  mov     r8d, 10h
0x14000734a  lea     rcx, [r14+48h]
0x14000734e  sub     r8, rax; Size
0x140007351  add     rcx, rax; void *
0x140007354  xor     edx, edx; Val
0x140007356  call    memset
0x14000735b  mov     al, 0Ch
0x14000735d  mov     [r14+0Ah], al
0x140007361  movzx   eax, byte ptr [r14+48h]
0x140007366  test    al, al
0x140007368  jz      loc_14000755E
0x14000736e  cmp     al, 15h
0x140007370  jz      loc_14000785D
0x140007376  cmp     al, 1Ah
0x140007378  jnz     loc_1400071E4
0x14000737e  movzx   edx, byte ptr [r14+4Ah]
0x140007383  xorps   xmm0, xmm0
0x140007386  movzx   r8d, byte ptr [r14+4Ch]
0x14000738b  movups  xmmword ptr [r14+48h], xmm0
0x140007390  movzx   eax, byte ptr [r14+4Ah]
0x140007395  movzx   ecx, al
0x140007398  mov     byte ptr [r14+48h], 5Ah ; 'Z'
0x14000739d  xor     cl, dl
0x14000739f  and     cl, 3Fh
0x1400073a2  xor     cl, al
0x1400073a4  mov     [r14+4Ah], cl
0x1400073a8  mov     [r14+50h], r8b
0x1400073ac  jmp     loc_1400071E4
0x1400073b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073b8  cmp     rcx, rdx
0x1400073bb  jnz     loc_140007728
0x1400073c1  xor     r9d, r9d
0x1400073c4  mov     r8, rbx
0x1400073c7  mov     rdx, rsi
0x1400073ca  mov     ecx, 50545346h
0x1400073cf  call    USBSTOR_LogEntry
0x1400073d4  lea     rcx, [rdi+790h]; Event
0x1400073db  xor     r8d, r8d; Wait
0x1400073de  xor     edx, edx; Increment
0x1400073e0  call    cs:__imp_KeSetEvent
0x1400073e7  nop     dword ptr [rax+rax+00h]
0x1400073ec  jmp     loc_1400072BD
0x1400073f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073f8  cmp     rcx, rdx
0x1400073fb  jz      short loc_14000740E
0x1400073fd  mov     eax, [rcx+2Ch]
0x140007400  test    al, 1
0x140007402  jz      short loc_14000740E
0x140007404  cmp     byte ptr [rcx+29h], 4
0x140007408  jnb     loc_1400075E3
0x14000740e  movsxd  r9, dword ptr [r14+18h]
0x140007412  mov     r8, rbx
0x140007415  mov     rdx, rsi
0x140007418  mov     ecx, 43445046h
0x14000741d  call    USBSTOR_LogEntry
0x140007422  test    dword ptr [rsi+30h], 2000h
0x140007429  jnz     loc_1400075D7
0x14000742f  mov     rax, [rbx+0B8h]
0x140007436  lea     rcx, USBSTOR_FdoSetPowerSxCompletion
0x14000743d  movups  xmm0, xmmword ptr [rax]
0x140007440  movups  xmmword ptr [rax-48h], xmm0
0x140007444  movups  xmm1, xmmword ptr [rax+10h]
0x140007448  movups  xmmword ptr [rax-38h], xmm1
0x14000744c  movups  xmm0, xmmword ptr [rax+20h]
0x140007450  movups  xmmword ptr [rax-28h], xmm0
0x140007454  movsd   xmm1, qword ptr [rax+30h]
0x140007459  movsd   qword ptr [rax-18h], xmm1
0x14000745e  mov     [rax-45h], r12b
0x140007462  mov     rdx, [rbx+0B8h]
0x140007469  movsxd  rax, dword ptr [rdi+788h]
0x140007470  mov     [rdx-10h], rcx
0x140007474  mov     [rdx-8], rax
0x140007478  mov     byte ptr [rdx-45h], 0E0h
0x14000747c  mov     rdx, rbx; Irp
0x14000747f  mov     rcx, [rdi+18h]; DeviceObject
0x140007483  call    cs:__imp_PoCallDriver
0x14000748a  nop     dword ptr [rax+rax+00h]
0x14000748f  jmp     loc_1400072BD
0x140007494  cmp     eax, 3Ch ; '<'
0x140007497  jbe     loc_140007187
0x14000749d  add     eax, 0FFFFFFEDh
0x1400074a0  jmp     loc_140007187
0x1400074a5  lea     rdx, [rbp+var_30]; LockHandle
0x1400074a9  lea     rcx, [rdi+90h]; SpinLock
0x1400074b0  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400074b7  nop     dword ptr [rax+rax+00h]
0x1400074bc  mov     r15d, [rdi+80h]
0x1400074c3  lea     rcx, [rbp+var_30]; LockHandle
0x1400074c7  and     r15d, 8
0x1400074cb  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400074d2  nop     dword ptr [rax+rax+00h]
0x1400074d7  movzx   ecx, [rbp+Irql]; Irql
0x1400074db  call    cs:__imp_IoReleaseCancelSpinLock
0x1400074e2  nop     dword ptr [rax+rax+00h]
0x1400074e7  xor     r9d, r9d
0x1400074ea  mov     r8, rbx
0x1400074ed  mov     rdx, rsi
0x1400074f0  mov     ecx, 334E4143h
0x1400074f5  call    USBSTOR_LogEntry
0x1400074fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140007501  lea     rax, WPP_GLOBAL_Control
0x140007508  cmp     rcx, rax
0x14000750b  jnz     loc_14000775F
0x140007511  mov     dword ptr [rbx+30h], 0C0000120h
0x140007518  xor     r8d, r8d
0x14000751b  mov     [rbx+38h], r12
0x14000751f  mov     rcx, rdi
0x140007522  mov     rdx, [r14+8]
0x140007526  mov     byte ptr [rdx+3], 2
0x14000752a  call    USBSTOR_FxPowerReference
0x14000752f  xor     edx, edx; PriorityBoost
0x140007531  mov     rcx, rbx; Irp
0x140007534  call    cs:__imp_IofCompleteRequest
0x14000753b  nop     dword ptr [rax+rax+00h]
0x140007540  test    r15d, r15d
0x140007543  jnz     loc_1400072AD
0x140007549  mov     rcx, r13
0x14000754c  call    UsbStorPumpNextRequest
0x140007551  mov     rcx, rsi; DeviceObject
0x140007554  call    UsbStorStartNextPacket
0x140007559  jmp     loc_1400072AD
0x14000755e  mov     eax, [r15+84h]
0x140007565  test    al, 4
0x140007567  jz      loc_1400071E4
0x14000756d  xorps   xmm0, xmm0
  ... truncated ...
```
