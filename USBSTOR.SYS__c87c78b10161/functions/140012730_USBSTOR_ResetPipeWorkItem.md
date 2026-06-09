# USBSTOR_ResetPipeWorkItem

- ea: `0x140012730`
- end: `0x140012884`
- name: `USBSTOR_ResetPipeWorkItem`
- size: `340`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400012d0`
- `0x140003630`
- `0x140003b90`
- `0x140007ff0`
- `0x140010664`
- `0x140011ec8`
- `0x140012730`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400127c8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400127c8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001286c`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14001286c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400127df`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400127df`

## pseudocode

```c
void __fastcall USBSTOR_ResetPipeWorkItem(struct _DEVICE_OBJECT *IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  char *DeviceExtension; // rbp
  int v6; // ebx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  USBSTOR_LogEntry(1464882002, IoObject, 0, 0);
  DeviceExtension = (char *)IoObject->DeviceExtension;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 135, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  USBSTOR_ResetPipe(IoObject, *(_QWORD *)(*((_QWORD *)DeviceExtension + 12) + 8LL));
  USBSTOR_ResetPipe(IoObject, *(_QWORD *)(*((_QWORD *)DeviceExtension + 13) + 8LL));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &LockHandle);
  v6 = *((_DWORD *)DeviceExtension + 32);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( (v6 & 4) != 0 )
  {
    if ( Context )
      UsbStorPumpNextRequest(Context);
    UsbStorStartNextPacket(IoObject);
  }
  else
  {
    USBSTOR_IssueRequestSenseCdb(IoObject, IoObject->CurrentIrp, 0);
  }
  USBSTOR_LogEntry(2003858290, IoObject, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 1832), USBSTOR_ResetPipeWorkItem, 0x20u);
}

```

## disassembly

```asm
0x140012730  push    rbx
0x140012732  push    rbp
0x140012733  push    rsi
0x140012734  push    rdi
0x140012735  push    r14
0x140012737  sub     rsp, 40h
0x14001273b  mov     rsi, rdx
0x14001273e  mov     rdi, rcx
0x140012741  mov     rdx, rcx
0x140012744  xorps   xmm0, xmm0
0x140012747  xor     eax, eax
0x140012749  mov     ecx, 57505352h
0x14001274e  xor     r9d, r9d
0x140012751  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x140012756  xor     r8d, r8d
0x140012759  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14001275e  call    USBSTOR_LogEntry
0x140012763  mov     rbp, [rdi+40h]
0x140012767  mov     rcx, cs:WPP_GLOBAL_Control
0x14001276e  lea     r14, WPP_GLOBAL_Control
0x140012775  cmp     rcx, r14
0x140012778  jz      short loc_14001279C
0x14001277a  mov     eax, [rcx+2Ch]
0x14001277d  test    al, 1
0x14001277f  jz      short loc_14001279C
0x140012781  cmp     byte ptr [rcx+29h], 5
0x140012785  jb      short loc_14001279C
0x140012787  mov     rcx, [rcx+18h]
0x14001278b  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140012792  mov     edx, 87h
0x140012797  call    WPP_SF_
0x14001279c  mov     rdx, [rbp+60h]
0x1400127a0  mov     rcx, rdi
0x1400127a3  mov     rdx, [rdx+8]
0x1400127a7  call    USBSTOR_ResetPipe
0x1400127ac  mov     rdx, [rbp+68h]
0x1400127b0  mov     rcx, rdi
0x1400127b3  mov     rdx, [rdx+8]
0x1400127b7  call    USBSTOR_ResetPipe
0x1400127bc  lea     rcx, [rbp+90h]; SpinLock
0x1400127c3  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x1400127c8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400127cf  nop     dword ptr [rax+rax+00h]
0x1400127d4  mov     ebx, [rbp+80h]
0x1400127da  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x1400127df  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400127e6  nop     dword ptr [rax+rax+00h]
0x1400127eb  bt      ebx, 2
0x1400127ef  jnb     short loc_140012808
0x1400127f1  test    rsi, rsi
0x1400127f4  jz      short loc_1400127FE
0x1400127f6  mov     rcx, rsi
0x1400127f9  call    UsbStorPumpNextRequest
0x1400127fe  mov     rcx, rdi; DeviceObject
0x140012801  call    UsbStorStartNextPacket
0x140012806  jmp     short loc_140012817
0x140012808  mov     rdx, [rdi+20h]; Irp
0x14001280c  xor     r8d, r8d; __int64
0x14001280f  mov     rcx, rdi; Object
0x140012812  call    USBSTOR_IssueRequestSenseCdb
0x140012817  xor     r9d, r9d
0x14001281a  xor     r8d, r8d
0x14001281d  mov     rdx, rdi
0x140012820  mov     ecx, 77707372h
0x140012825  call    USBSTOR_LogEntry
0x14001282a  mov     rcx, cs:WPP_GLOBAL_Control
0x140012831  cmp     rcx, r14
0x140012834  jz      short loc_140012858
0x140012836  mov     eax, [rcx+2Ch]
0x140012839  test    al, 1
0x14001283b  jz      short loc_140012858
0x14001283d  cmp     byte ptr [rcx+29h], 5
0x140012841  jb      short loc_140012858
0x140012843  mov     rcx, [rcx+18h]
0x140012847  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14001284e  mov     edx, 88h
0x140012853  call    WPP_SF_
0x140012858  lea     rcx, [rbp+728h]; RemoveLock
0x14001285f  mov     r8d, 20h ; ' '; RemlockSize
0x140012865  lea     rdx, USBSTOR_ResetPipeWorkItem; Tag
0x14001286c  call    cs:__imp_IoReleaseRemoveLockEx
0x140012873  nop     dword ptr [rax+rax+00h]
0x140012878  add     rsp, 40h
0x14001287c  pop     r14
0x14001287e  pop     rdi
0x14001287f  pop     rsi
0x140012880  pop     rbp
0x140012881  pop     rbx
0x140012882  retn
```
