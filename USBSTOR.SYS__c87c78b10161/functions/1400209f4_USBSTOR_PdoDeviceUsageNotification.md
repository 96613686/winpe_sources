# USBSTOR_PdoDeviceUsageNotification

- ea: `0x1400209f4`
- end: `0x140020c87`
- name: `USBSTOR_PdoDeviceUsageNotification`
- size: `659`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140010664`
- `0x14001f964`
- `0x1400209f4`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceState` at `0x140020ae9`
- `ntoskrnl!IoInvalidateDeviceState` at `0x140020ae9`
- `ntoskrnl!IoFreeIrp` at `0x140020bb6`
- `ntoskrnl!IoFreeIrp` at `0x140020bb6`
- `ntoskrnl!IofCallDriver` at `0x140020b78`
- `ntoskrnl!IofCallDriver` at `0x140020c20`
- `ntoskrnl!IofCallDriver` at `0x140020b78`
- `ntoskrnl!IofCallDriver` at `0x140020c20`
- `ntoskrnl!KeInitializeEvent` at `0x140020b1b`
- `ntoskrnl!KeInitializeEvent` at `0x140020b1b`
- `ntoskrnl!IofCompleteRequest` at `0x140020ada`
- `ntoskrnl!IofCompleteRequest` at `0x140020ada`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020ba3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140020ba3`
- `ntoskrnl!IoGetAttachedDevice` at `0x140020a8b`
- `ntoskrnl!IoGetAttachedDevice` at `0x140020a8b`
- `ntoskrnl!IoAllocateIrp` at `0x140020aa4`
- `ntoskrnl!IoAllocateIrp` at `0x140020aa4`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoDeviceUsageNotification(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r12
  PVOID DeviceExtension; // rsi
  int Options; // r15d
  BOOLEAN Lock; // r13
  int Status; // ebx
  PIRP v9; // rax
  IRP *v10; // r14
  struct _IO_STACK_LOCATION *v11; // rax
  struct _IO_STACK_LOCATION *v12; // rcx
  ULONG Flags; // eax
  ULONG v14; // eax
  struct _KEVENT Event; // [rsp+30h] [rbp-68h] BYREF
  PDEVICE_OBJECT DeviceObjecta; // [rsp+A0h] [rbp+8h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = DeviceObject->DeviceExtension;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Lock = CurrentStackLocation->Parameters.SetLock.Lock;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 147, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1314210896, DeviceObject, Irp, 0);
  if ( (unsigned int)(Options - 1) > 3 )
  {
    ++Irp->CurrentLocation;
    ++Irp->Tail.Overlay.CurrentStackLocation;
    Status = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), Irp);
    goto LABEL_26;
  }
  if ( !*((_BYTE *)DeviceExtension + 70) || !Lock )
  {
    DeviceObjecta = IoGetAttachedDevice(*((PDEVICE_OBJECT *)DeviceExtension + 2));
    v9 = IoAllocateIrp(DeviceObjecta->StackSize, 0);
    v10 = v9;
    if ( v9 )
    {
      v9->IoStatus.Status = -1073741637;
      memset(&Event, 0, sizeof(Event));
      KeInitializeEvent(&Event, NotificationEvent, 0);
      v11 = v10->Tail.Overlay.CurrentStackLocation;
      v11[-1].CompletionRoutine = USBSTOR_SyncCompletionRoutine;
      v11[-1].Context = &Event;
      v11[-1].Control = -32;
      v12 = v10->Tail.Overlay.CurrentStackLocation;
      v12[-1].MajorFunction = CurrentStackLocation->MajorFunction;
      v12[-1].MinorFunction = CurrentStackLocation->MinorFunction;
      v12[-1].FileObject = CurrentStackLocation->FileObject;
      v12[-1].Parameters.SetLock.Lock = Lock;
      v12[-1].Parameters.Create.Options = Options;
      if ( IofCallDriver(DeviceObjecta, v10) == 259 )
        KeWaitForSingleObject(&Event, Suspended, 0, 0, 0);
      Status = v10->IoStatus.Status;
      IoFreeIrp(v10);
      if ( Status >= 0 && Options <= 3 )
      {
        if ( Lock )
          _InterlockedIncrement((volatile signed __int32 *)DeviceExtension + 200);
        else
          _InterlockedDecrement((volatile signed __int32 *)DeviceExtension + 200);
        Flags = DeviceObject->Flags;
        if ( *((_DWORD *)DeviceExtension + 200) )
          v14 = Flags & 0xFFFFDFFF;
        else
          v14 = Flags | 0x2000;
        DeviceObject->Flags = v14;
        goto LABEL_13;
      }
    }
    else
    {
      Status = -1073741670;
    }
    if ( Options == 4 )
      USBSTOR_DetectPortableWorkspace(DeviceObject);
    goto LABEL_13;
  }
  Status = -1073741637;
LABEL_13:
  Irp->IoStatus.Status = Status;
  IofCompleteRequest(Irp, 0);
  IoInvalidateDeviceState(DeviceObject);
LABEL_26:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 148, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1853187184, Status, 0, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400209f4  push    rbx
0x1400209f6  push    rbp
0x1400209f7  push    rsi
0x1400209f8  push    rdi
0x1400209f9  push    r12
0x1400209fb  push    r13
0x1400209fd  push    r14
0x1400209ff  push    r15
0x140020a01  sub     rsp, 58h
0x140020a05  mov     r12, [rdx+0B8h]
0x140020a0c  mov     rdi, rdx
0x140020a0f  mov     rsi, [rcx+40h]
0x140020a13  mov     rbp, rcx
0x140020a16  mov     r15d, [r12+10h]
0x140020a1b  mov     r13b, [r12+8]
0x140020a20  mov     rcx, cs:WPP_GLOBAL_Control
0x140020a27  lea     r14, WPP_GLOBAL_Control
0x140020a2e  cmp     rcx, r14
0x140020a31  jz      short loc_140020A55
0x140020a33  mov     eax, [rcx+2Ch]
0x140020a36  test    al, 2
0x140020a38  jz      short loc_140020A55
0x140020a3a  cmp     byte ptr [rcx+29h], 4
0x140020a3e  jb      short loc_140020A55
0x140020a40  mov     rcx, [rcx+18h]
0x140020a44  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140020a4b  mov     edx, 93h
0x140020a50  call    WPP_SF_
0x140020a55  xor     r9d, r9d
0x140020a58  mov     r8, rdi
0x140020a5b  mov     rdx, rbp
0x140020a5e  mov     ecx, 4E554450h
0x140020a63  call    USBSTOR_LogEntry
0x140020a68  lea     eax, [r15-1]
0x140020a6c  cmp     eax, 3
0x140020a6f  ja      loc_140020C0E
0x140020a75  cmp     byte ptr [rsi+46h], 0
0x140020a79  jz      short loc_140020A87
0x140020a7b  test    r13b, r13b
0x140020a7e  jz      short loc_140020A87
0x140020a80  mov     ebx, 0C00000BBh
0x140020a85  jmp     short loc_140020AD2
0x140020a87  mov     rcx, [rsi+10h]; DeviceObject
0x140020a8b  call    cs:__imp_IoGetAttachedDevice
0x140020a92  nop     dword ptr [rax+rax+00h]
0x140020a97  xor     edx, edx; ChargeQuota
0x140020a99  mov     [rsp+98h+DeviceObject], rax
0x140020aa1  mov     cl, [rax+4Ch]; StackSize
0x140020aa4  call    cs:__imp_IoAllocateIrp
0x140020aab  nop     dword ptr [rax+rax+00h]
0x140020ab0  mov     r14, rax
0x140020ab3  test    rax, rax
0x140020ab6  jnz     short loc_140020AFA
0x140020ab8  mov     ebx, 0C000009Ah
0x140020abd  cmp     r15d, 4
0x140020ac1  jnz     short loc_140020ACB
0x140020ac3  mov     rcx, rbp; DeviceObject
0x140020ac6  call    USBSTOR_DetectPortableWorkspace
0x140020acb  lea     r14, WPP_GLOBAL_Control
0x140020ad2  xor     edx, edx; PriorityBoost
0x140020ad4  mov     [rdi+30h], ebx
0x140020ad7  mov     rcx, rdi; Irp
0x140020ada  call    cs:__imp_IofCompleteRequest
0x140020ae1  nop     dword ptr [rax+rax+00h]
0x140020ae6  mov     rcx, rbp; PhysicalDeviceObject
0x140020ae9  call    cs:__imp_IoInvalidateDeviceState
0x140020af0  nop     dword ptr [rax+rax+00h]
0x140020af5  jmp     loc_140020C2E
0x140020afa  xorps   xmm0, xmm0
0x140020afd  mov     dword ptr [r14+30h], 0C00000BBh
0x140020b05  xor     eax, eax
0x140020b07  lea     rcx, [rsp+98h+Event]; Event
0x140020b0c  xor     r8d, r8d; State
0x140020b0f  mov     [rsp+98h+Event.Header.WaitListHead.Blink], rax
0x140020b14  xor     edx, edx; Type
0x140020b16  movups  xmmword ptr [rsp+98h+Event.Header], xmm0
0x140020b1b  call    cs:__imp_KeInitializeEvent
0x140020b22  nop     dword ptr [rax+rax+00h]
0x140020b27  mov     rax, [r14+0B8h]
0x140020b2e  lea     rcx, USBSTOR_SyncCompletionRoutine
0x140020b35  mov     rdx, r14; Irp
0x140020b38  mov     [rax-10h], rcx
0x140020b3c  lea     rcx, [rsp+98h+Event]
0x140020b41  mov     [rax-8], rcx
0x140020b45  mov     byte ptr [rax-45h], 0E0h
0x140020b49  mov     al, [r12]
0x140020b4d  mov     rcx, [r14+0B8h]
0x140020b54  mov     [rcx-48h], al
0x140020b57  mov     al, [r12+1]
0x140020b5c  mov     [rcx-47h], al
0x140020b5f  mov     rax, [r12+30h]
0x140020b64  mov     [rcx-18h], rax
0x140020b68  mov     [rcx-40h], r13b
0x140020b6c  mov     [rcx-38h], r15d
0x140020b70  mov     rcx, [rsp+98h+DeviceObject]; DeviceObject
0x140020b78  call    cs:__imp_IofCallDriver
0x140020b7f  nop     dword ptr [rax+rax+00h]
0x140020b84  cmp     eax, 103h
0x140020b89  jnz     short loc_140020BAF
0x140020b8b  xor     r9d, r9d; Alertable
0x140020b8e  mov     [rsp+98h+Timeout], 0; Timeout
0x140020b97  xor     r8d, r8d; WaitMode
0x140020b9a  lea     rcx, [rsp+98h+Event]; Object
0x140020b9f  lea     edx, [r9+5]; WaitReason
0x140020ba3  call    cs:__imp_KeWaitForSingleObject
0x140020baa  nop     dword ptr [rax+rax+00h]
0x140020baf  mov     ebx, [r14+30h]
0x140020bb3  mov     rcx, r14; Irp
0x140020bb6  call    cs:__imp_IoFreeIrp
0x140020bbd  nop     dword ptr [rax+rax+00h]
0x140020bc2  test    ebx, ebx
0x140020bc4  js      loc_140020ABD
0x140020bca  cmp     r15d, 3
0x140020bce  jg      loc_140020ABD
0x140020bd4  test    r13b, r13b
0x140020bd7  jz      short loc_140020BE2
0x140020bd9  lock inc dword ptr [rsi+320h]
0x140020be0  jmp     short loc_140020BE9
0x140020be2  lock dec dword ptr [rsi+320h]
0x140020be9  cmp     dword ptr [rsi+320h], 0
0x140020bf0  lea     r14, WPP_GLOBAL_Control
0x140020bf7  mov     eax, [rbp+30h]
0x140020bfa  jz      short loc_140020C08
0x140020bfc  btr     eax, 0Dh
0x140020c00  mov     [rbp+30h], eax
0x140020c03  jmp     loc_140020AD2
0x140020c08  bts     eax, 0Dh
0x140020c0c  jmp     short loc_140020C00
0x140020c0e  inc     byte ptr [rdi+43h]
0x140020c11  mov     rdx, rdi; Irp
0x140020c14  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140020c1c  mov     rcx, [rsi+10h]; DeviceObject
0x140020c20  call    cs:__imp_IofCallDriver
0x140020c27  nop     dword ptr [rax+rax+00h]
0x140020c2c  mov     ebx, eax
0x140020c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140020c35  cmp     rcx, r14
0x140020c38  jz      short loc_140020C60
0x140020c3a  mov     edx, [rcx+2Ch]
0x140020c3d  test    dl, 2
0x140020c40  jz      short loc_140020C60
0x140020c42  cmp     byte ptr [rcx+29h], 4
0x140020c46  jb      short loc_140020C60
0x140020c48  mov     rcx, [rcx+18h]
0x140020c4c  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140020c53  mov     edx, 94h
0x140020c58  mov     r9d, ebx
0x140020c5b  call    WPP_SF_d
0x140020c60  movsxd  rdx, ebx
0x140020c63  xor     r9d, r9d
0x140020c66  xor     r8d, r8d
0x140020c69  mov     ecx, 6E756470h
0x140020c6e  call    USBSTOR_LogEntry
0x140020c73  mov     eax, ebx
0x140020c75  add     rsp, 58h
0x140020c79  pop     r15
0x140020c7b  pop     r14
0x140020c7d  pop     r13
0x140020c7f  pop     r12
0x140020c81  pop     rdi
0x140020c82  pop     rsi
0x140020c83  pop     rbp
0x140020c84  pop     rbx
0x140020c85  retn
```
