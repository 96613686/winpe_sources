# USBSTOR_IssueAsyncNotificationRequest

- ea: `0x140011c10`
- end: `0x140011e33`
- name: `USBSTOR_IssueAsyncNotificationRequest`
- size: `547`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011820`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140010664`
- `0x140011c10`
- `0x140013d40`

## import_xrefs

- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140011d75`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140011d75`
- `ntoskrnl!IofCallDriver` at `0x140011d9f`
- `ntoskrnl!IofCallDriver` at `0x140011d9f`
- `ntoskrnl!IoReuseIrp` at `0x140011c8e`
- `ntoskrnl!IoReuseIrp` at `0x140011c8e`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140011ccc`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140011ccc`
- `ntoskrnl!IoAllocateIrp` at `0x140011e0a`
- `ntoskrnl!IoAllocateIrp` at `0x140011e0a`

## pseudocode

```c
__int64 __fastcall USBSTOR_IssueAsyncNotificationRequest(struct _DEVICE_OBJECT *Context)
{
  char *DeviceExtension; // rsi
  IRP *v3; // rdi
  NTSTATUS v4; // ebx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v6; // rax
  PIRP Irp; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  DeviceExtension = (char *)Context->DeviceExtension;
  if ( (*((_DWORD *)DeviceExtension + 32) & 0x80u) == 0 )
  {
    v3 = (IRP *)*((_QWORD *)DeviceExtension + 45);
    if ( v3 )
    {
      IoReuseIrp(*((PIRP *)DeviceExtension + 45), -1073741823);
    }
    else
    {
      Irp = IoAllocateIrp(*(_BYTE *)(*((_QWORD *)DeviceExtension + 3) + 76LL), 0);
      *((_QWORD *)DeviceExtension + 45) = Irp;
      v3 = Irp;
      if ( !Irp )
      {
        v4 = -1073741670;
        goto LABEL_13;
      }
    }
    USBSTOR_LogEntry(1414416705, Context, v3, 0);
    v4 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 1832), v3, File, 1u, 0x20u);
    if ( v4 >= 0 )
    {
      memset(DeviceExtension + 532, 0, 0x7Cu);
      *((_DWORD *)DeviceExtension + 132) = 589952;
      *((_QWORD *)DeviceExtension + 69) = *(_QWORD *)(*((_QWORD *)DeviceExtension + 14) + 8LL);
      *((_QWORD *)DeviceExtension + 71) = DeviceExtension + 656;
      *((_DWORD *)DeviceExtension + 140) = 3;
      *((_DWORD *)DeviceExtension + 141) = 512;
      *((_QWORD *)DeviceExtension + 72) = 0;
      CurrentStackLocation = v3->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)(DeviceExtension + 528);
      CurrentStackLocation[-1].MajorFunction = 15;
      CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
      CurrentStackLocation[-1].DeviceObject = (PDEVICE_OBJECT)*((_QWORD *)DeviceExtension + 3);
      *((_DWORD *)DeviceExtension + 32) |= 0x80u;
      if ( IoSetCompletionRoutineEx(
             Context,
             v3,
             (PIO_COMPLETION_ROUTINE)USBSTOR_AsyncNotifyInterruptPipeCompletion,
             Context,
             1u,
             1u,
             1u) < 0 )
      {
        v6 = v3->Tail.Overlay.CurrentStackLocation;
        v6[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)USBSTOR_AsyncNotifyInterruptPipeCompletion;
        v6[-1].Context = Context;
        v6[-1].Control = -32;
      }
      v4 = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 3), v3);
    }
  }
  else
  {
    v3 = 0;
    v4 = -1073741823;
  }
LABEL_13:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  USBSTOR_LogEntry(1953392993, Context, v3, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140011c10  push    rbx
0x140011c12  push    rbp
0x140011c13  push    rsi
0x140011c14  push    rdi
0x140011c15  push    r14
0x140011c17  push    r15
0x140011c19  sub     rsp, 48h
0x140011c1d  mov     rbp, rcx
0x140011c20  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c27  lea     r14, WPP_GLOBAL_Control
0x140011c2e  cmp     rcx, r14
0x140011c31  jz      short loc_140011C55
0x140011c33  mov     eax, [rcx+2Ch]
0x140011c36  test    al, 1
0x140011c38  jz      short loc_140011C55
0x140011c3a  cmp     byte ptr [rcx+29h], 5
0x140011c3e  jb      short loc_140011C55
0x140011c40  mov     rcx, [rcx+18h]
0x140011c44  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140011c4b  mov     edx, 5Ah ; 'Z'
0x140011c50  call    WPP_SF_
0x140011c55  mov     rsi, [rbp+40h]
0x140011c59  mov     r15d, 80h
0x140011c5f  mov     eax, [rsi+80h]
0x140011c65  test    r15b, al
0x140011c68  jz      short loc_140011C76
0x140011c6a  xor     edi, edi
0x140011c6c  mov     ebx, 0C0000001h
0x140011c71  jmp     loc_140011DAD
0x140011c76  mov     rdi, [rsi+168h]
0x140011c7d  test    rdi, rdi
0x140011c80  jz      loc_140011E01
0x140011c86  mov     edx, 0C0000001h; Iostatus
0x140011c8b  mov     rcx, rdi; Irp
0x140011c8e  call    cs:__imp_IoReuseIrp
0x140011c95  nop     dword ptr [rax+rax+00h]
0x140011c9a  xor     r9d, r9d
0x140011c9d  mov     r8, rdi
0x140011ca0  mov     rdx, rbp
0x140011ca3  mov     ecx, 544E4941h
0x140011ca8  call    USBSTOR_LogEntry
0x140011cad  lea     rcx, [rsi+728h]; RemoveLock
0x140011cb4  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x140011cbc  mov     r9d, 1; Line
0x140011cc2  lea     r8, File; File
0x140011cc9  mov     rdx, rdi; Tag
0x140011ccc  call    cs:__imp_IoAcquireRemoveLockEx
0x140011cd3  nop     dword ptr [rax+rax+00h]
0x140011cd8  mov     ebx, eax
0x140011cda  test    eax, eax
0x140011cdc  js      loc_140011DAD
0x140011ce2  xor     edx, edx; Val
0x140011ce4  lea     rcx, [rsi+214h]; void *
0x140011ceb  lea     rbx, [rsi+210h]
0x140011cf2  lea     r8d, [rdx+7Ch]; Size
0x140011cf6  call    memset
0x140011cfb  mov     dword ptr [rbx], 90080h
0x140011d01  mov     r9, rbp; Context
0x140011d04  mov     rax, [rsi+70h]
0x140011d08  mov     rdx, rdi; Irp
0x140011d0b  mov     [rsp+78h+InvokeOnCancel], 1; InvokeOnCancel
0x140011d10  mov     [rsp+78h+InvokeOnError], 1; InvokeOnError
0x140011d15  mov     byte ptr [rsp+78h+RemlockSize], 1; InvokeOnSuccess
0x140011d1a  mov     rcx, [rax+8]
0x140011d1e  lea     rax, [rsi+290h]
0x140011d25  mov     [rbx+18h], rcx
0x140011d29  mov     [rbx+28h], rax
0x140011d2d  mov     dword ptr [rbx+20h], 3
0x140011d34  mov     dword ptr [rbx+24h], 200h
0x140011d3b  mov     qword ptr [rbx+30h], 0
0x140011d43  mov     rcx, [rdi+0B8h]
0x140011d4a  mov     [rcx-40h], rbx
0x140011d4e  lea     rbx, USBSTOR_AsyncNotifyInterruptPipeCompletion
0x140011d55  mov     byte ptr [rcx-48h], 0Fh
0x140011d59  mov     r8, rbx; CompletionRoutine
0x140011d5c  mov     dword ptr [rcx-30h], 220003h
0x140011d63  mov     rax, [rsi+18h]
0x140011d67  mov     [rcx-20h], rax
0x140011d6b  mov     rcx, rbp; DeviceObject
0x140011d6e  or      [rsi+80h], r15d
0x140011d75  call    cs:__imp_IoSetCompletionRoutineEx
0x140011d7c  nop     dword ptr [rax+rax+00h]
0x140011d81  test    eax, eax
0x140011d83  jns     short loc_140011D98
0x140011d85  mov     rax, [rdi+0B8h]
0x140011d8c  mov     [rax-10h], rbx
0x140011d90  mov     [rax-8], rbp
0x140011d94  mov     byte ptr [rax-45h], 0E0h
0x140011d98  mov     rcx, [rsi+18h]; DeviceObject
0x140011d9c  mov     rdx, rdi; Irp
0x140011d9f  call    cs:__imp_IofCallDriver
0x140011da6  nop     dword ptr [rax+rax+00h]
0x140011dab  mov     ebx, eax
0x140011dad  mov     rcx, cs:WPP_GLOBAL_Control
0x140011db4  cmp     rcx, r14
0x140011db7  jz      short loc_140011DDE
0x140011db9  mov     eax, [rcx+2Ch]
0x140011dbc  test    al, 1
0x140011dbe  jz      short loc_140011DDE
0x140011dc0  cmp     byte ptr [rcx+29h], 5
0x140011dc4  jb      short loc_140011DDE
0x140011dc6  mov     rcx, [rcx+18h]
0x140011dca  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140011dd1  mov     edx, 5Bh ; '['
0x140011dd6  mov     r9d, ebx
0x140011dd9  call    WPP_SF_d
0x140011dde  movsxd  r9, ebx
0x140011de1  mov     r8, rdi
0x140011de4  mov     rdx, rbp
0x140011de7  mov     ecx, 746E6961h
0x140011dec  call    USBSTOR_LogEntry
0x140011df1  mov     eax, ebx
0x140011df3  add     rsp, 48h
0x140011df7  pop     r15
0x140011df9  pop     r14
0x140011dfb  pop     rdi
0x140011dfc  pop     rsi
0x140011dfd  pop     rbp
0x140011dfe  pop     rbx
0x140011dff  retn
0x140011e01  mov     rcx, [rsi+18h]
0x140011e05  xor     edx, edx; ChargeQuota
0x140011e07  mov     cl, [rcx+4Ch]; StackSize
0x140011e0a  call    cs:__imp_IoAllocateIrp
0x140011e11  nop     dword ptr [rax+rax+00h]
0x140011e16  mov     [rsi+168h], rax
0x140011e1d  mov     rdi, rax
0x140011e20  test    rax, rax
0x140011e23  jnz     loc_140011C9A
0x140011e29  mov     ebx, 0C000009Ah
0x140011e2e  jmp     loc_140011DAD
```
