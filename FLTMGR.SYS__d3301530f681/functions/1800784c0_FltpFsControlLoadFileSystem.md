# FltpFsControlLoadFileSystem

- ea: `0x1800784c0`
- end: `0x180078647`
- name: `FltpFsControlLoadFileSystem`
- size: `391`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006ee20`

## callees

- `0x180003380`
- `0x180009f20`
- `0x18001cd80`
- `0x18001fd80`
- `0x180020a00`
- `0x1800682b0`
- `0x1800784c0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x180078520`
- `ntoskrnl!KeInitializeEvent` at `0x180078520`
- `ntoskrnl!IoAttachDeviceToDeviceStackSafe` at `0x180078602`
- `ntoskrnl!IoAttachDeviceToDeviceStackSafe` at `0x180078602`
- `ntoskrnl!IoDetachDevice` at `0x18007857b`
- `ntoskrnl!IoDetachDevice` at `0x18007857b`
- `ntoskrnl!IofCompleteRequest` at `0x18007862d`
- `ntoskrnl!IofCompleteRequest` at `0x18007862d`

## pseudocode

```c
__int64 __fastcall FltpFsControlLoadFileSystem(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  unsigned __int16 *DeviceExtension; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v6; // rax
  int v7; // edx
  int v8; // r8d
  int v9; // r8d
  unsigned int Status; // ebx
  int v12; // [rsp+20h] [rbp-68h]
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  DeviceExtension = (unsigned __int16 *)DeviceObject->DeviceExtension;
  memset(&Event, 0, sizeof(Event));
  if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
    McTemplateU0spw_EtwWriteTransfer(
      (_DWORD)DeviceObject,
      (unsigned int)fltmgr_c7670,
      (unsigned int)"FltpFsControlLoadFileSystem",
      (_DWORD)DeviceObject,
      DeviceExtension[24] >> 1,
      *((_QWORD *)DeviceExtension + 7));
  KeInitializeEvent(&Event, NotificationEvent, 0);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v6 = Irp->Tail.Overlay.CurrentStackLocation;
  v6[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&FltpFsControlCompletion;
  v6[-1].Context = &Event;
  v6[-1].Control = -32;
  IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 1));
  if ( (unsigned int)FltpCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 1), Irp) == 259 )
    FltpCancellableWaitForIo(&Event, Irp);
  if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 8) != 0 )
    McTemplateU0sppwd_EtwWriteTransfer(
      DeviceExtension[24] >> 1,
      v7,
      v8,
      (_DWORD)DeviceObject,
      v12,
      DeviceExtension[24] >> 1,
      *((_QWORD *)DeviceExtension + 7),
      Irp->IoStatus.Status);
  if ( (int)FltpDbgStatus((unsigned int)Irp->IoStatus.Status, "minkernel\\fs\\filtermgr\\filter\\fltmgr.c", 7733, 0) >= 0
    || Irp->IoStatus.Status == -1073741554 )
  {
    *((_QWORD *)DeviceExtension + 1) = 0;
    FltpCleanupDeviceObject(DeviceObject, 8, v9);
  }
  else
  {
    IoAttachDeviceToDeviceStackSafe(
      DeviceObject,
      *((PDEVICE_OBJECT *)DeviceExtension + 1),
      (PDEVICE_OBJECT *)DeviceExtension + 1);
  }
  Status = Irp->IoStatus.Status;
  IofCompleteRequest(Irp, 0);
  return Status;
}

```

## disassembly

```asm
0x1800784c0  push    rbx
0x1800784c2  push    rbp
0x1800784c3  push    rsi
0x1800784c4  push    rdi
0x1800784c5  push    r14
0x1800784c7  sub     rsp, 60h
0x1800784cb  mov     rbp, [rcx+40h]
0x1800784cf  xor     eax, eax
0x1800784d1  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x1800784d8  xorps   xmm0, xmm0
0x1800784db  mov     rdi, rdx
0x1800784de  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x1800784e3  mov     rsi, rcx
0x1800784e6  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x1800784eb  jz      short loc_180078516
0x1800784ed  movzx   edx, word ptr [rbp+30h]
0x1800784f1  lea     r8, aFltpfscontroll; "FltpFsControlLoadFileSystem"
0x1800784f8  mov     rax, [rbp+38h]
0x1800784fc  mov     r9, rcx
0x1800784ff  shr     edx, 1
0x180078501  mov     [rsp+88h+var_60], rax
0x180078506  mov     [rsp+88h+var_68], edx
0x18007850a  lea     rdx, fltmgr_c7670
0x180078511  call    McTemplateU0spw_EtwWriteTransfer
0x180078516  xor     r8d, r8d; State
0x180078519  lea     rcx, [rsp+88h+Event]; Event
0x18007851e  xor     edx, edx; Type
0x180078520  call    cs:__imp_KeInitializeEvent
0x180078527  nop     dword ptr [rax+rax+00h]
0x18007852c  mov     rax, [rdi+0B8h]
0x180078533  lea     rcx, FltpFsControlCompletion
0x18007853a  movups  xmm0, xmmword ptr [rax]
0x18007853d  movups  xmmword ptr [rax-48h], xmm0
0x180078541  movups  xmm1, xmmword ptr [rax+10h]
0x180078545  movups  xmmword ptr [rax-38h], xmm1
0x180078549  movups  xmm0, xmmword ptr [rax+20h]
0x18007854d  movups  xmmword ptr [rax-28h], xmm0
0x180078551  movsd   xmm1, qword ptr [rax+30h]
0x180078556  movsd   qword ptr [rax-18h], xmm1
0x18007855b  mov     byte ptr [rax-45h], 0
0x18007855f  mov     rax, [rdi+0B8h]
0x180078566  mov     [rax-10h], rcx
0x18007856a  lea     rcx, [rsp+88h+Event]
0x18007856f  mov     [rax-8], rcx
0x180078573  mov     byte ptr [rax-45h], 0E0h
0x180078577  mov     rcx, [rbp+8]; TargetDevice
0x18007857b  call    cs:__imp_IoDetachDevice
0x180078582  nop     dword ptr [rax+rax+00h]
0x180078587  mov     rcx, [rbp+8]; DeviceObject
0x18007858b  mov     rdx, rdi; Irp
0x18007858e  call    FltpCallDriver
0x180078593  cmp     eax, 103h
0x180078598  jnz     short loc_1800785A7
0x18007859a  mov     rdx, rdi; Irp
0x18007859d  lea     rcx, [rsp+88h+Event]; Object
0x1800785a2  call    FltpCancellableWaitForIo
0x1800785a7  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 8
0x1800785ae  jz      short loc_1800785D2
0x1800785b0  mov     eax, [rdi+30h]
0x1800785b3  mov     r9, rsi
0x1800785b6  movzx   ecx, word ptr [rbp+30h]
0x1800785ba  mov     [rsp+88h+var_50], eax
0x1800785be  mov     rax, [rbp+38h]
0x1800785c2  shr     ecx, 1
0x1800785c4  mov     [rsp+88h+var_58], rax
0x1800785c9  mov     dword ptr [rsp+88h+var_60], ecx
0x1800785cd  call    McTemplateU0sppwd_EtwWriteTransfer
0x1800785d2  mov     ecx, [rdi+30h]
0x1800785d5  lea     rdx, aMinkernelFsFil_28; "minkernel\\fs\\filtermgr\\filter\\fltmg"...
0x1800785dc  mov     r8d, 1E35h
0x1800785e2  xor     r9d, r9d
0x1800785e5  call    FltpDbgStatus
0x1800785ea  test    eax, eax
0x1800785ec  jns     short loc_180078610
0x1800785ee  cmp     dword ptr [rdi+30h], 0C000010Eh
0x1800785f5  jz      short loc_180078610
0x1800785f7  mov     rdx, [rbp+8]; TargetDevice
0x1800785fb  lea     r8, [rbp+8]; AttachedToDeviceObject
0x1800785ff  mov     rcx, rsi; SourceDevice
0x180078602  call    cs:__imp_IoAttachDeviceToDeviceStackSafe
0x180078609  nop     dword ptr [rax+rax+00h]
0x18007860e  jmp     short loc_180078625
0x180078610  mov     edx, 8
0x180078615  mov     qword ptr [rbp+8], 0
0x18007861d  mov     rcx, rsi; DeviceObject
0x180078620  call    FltpCleanupDeviceObject
0x180078625  mov     ebx, [rdi+30h]
0x180078628  xor     edx, edx; PriorityBoost
0x18007862a  mov     rcx, rdi; Irp
0x18007862d  call    cs:__imp_IofCompleteRequest
0x180078634  nop     dword ptr [rax+rax+00h]
0x180078639  mov     eax, ebx
0x18007863b  add     rsp, 60h
0x18007863f  pop     r14
0x180078641  pop     rdi
0x180078642  pop     rsi
0x180078643  pop     rbp
0x180078644  pop     rbx
0x180078645  retn
```
