# USBSTOR_FdoSetPowerD0Completion

- ea: `0x1400084c0`
- end: `0x140008586`
- name: `USBSTOR_FdoSetPowerD0Completion`
- size: `198`
- prototype: `__int64 __fastcall(PVOID Object, PIRP Irp)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003630`
- `0x140007ff0`
- `0x1400084c0`
- `0x1400090a8`
- `0x14000de94`
- `0x140010eb8`
- `0x140012318`

## import_xrefs

- `ntoskrnl!PoStartNextPowerIrp` at `0x14000856c`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000856c`

## pseudocode

```c
__int64 __fastcall USBSTOR_FdoSetPowerD0Completion(struct _DEVICE_OBJECT *Object, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  char *DeviceExtension; // rbp
  __int64 LowPart; // r14
  __int64 Status; // rsi
  __int64 v8; // rax
  __int64 v9; // r8

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = (char *)Object->DeviceExtension;
  LowPart = (int)CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( Irp->PendingReturned )
    CurrentStackLocation->Control |= 1u;
  Status = Irp->IoStatus.Status;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v8 = PowerDeviceStateString((unsigned int)LowPart);
    WPP_SF_qqsD(*(_QWORD *)(v9 + 24), 40, v9, (_DWORD)Object, (char)Irp, v8, Status);
  }
  USBSTOR_LogEntry(1664119654, Object, LowPart, Status);
  if ( (unsigned __int8)USBSTOR_IsDeviceAsyncCapable(DeviceExtension) )
    USBSTOR_QueueAsyncNotification(Object, DeviceExtension);
  UsbStorStartNextPacket(Object);
  PoStartNextPowerIrp(Irp);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400084c0  push    rbx
0x1400084c2  push    rbp
0x1400084c3  push    rsi
0x1400084c4  push    rdi
0x1400084c5  push    r14
0x1400084c7  sub     rsp, 40h
0x1400084cb  cmp     byte ptr [rdx+41h], 0
0x1400084cf  mov     rbx, rdx
0x1400084d2  mov     rax, [rdx+0B8h]
0x1400084d9  mov     rdi, rcx
0x1400084dc  mov     rbp, [rcx+40h]
0x1400084e0  movsxd  r14, dword ptr [rax+18h]
0x1400084e4  jz      short loc_1400084EA
0x1400084e6  or      byte ptr [rax+3], 1
0x1400084ea  movsxd  rsi, dword ptr [rdx+30h]
0x1400084ee  mov     r8, cs:WPP_GLOBAL_Control
0x1400084f5  lea     rax, WPP_GLOBAL_Control
0x1400084fc  cmp     r8, rax
0x1400084ff  jz      short loc_140008537
0x140008501  mov     eax, [r8+2Ch]
0x140008505  test    al, 4
0x140008507  jz      short loc_140008537
0x140008509  cmp     byte ptr [r8+29h], 4
0x14000850e  jb      short loc_140008537
0x140008510  mov     ecx, r14d
0x140008513  call    PowerDeviceStateString
0x140008518  mov     rcx, [r8+18h]
0x14000851c  mov     edx, 28h ; '('
0x140008521  mov     [rsp+68h+var_38], esi
0x140008525  mov     r9, rdi
0x140008528  mov     [rsp+68h+var_40], rax
0x14000852d  mov     [rsp+68h+var_48], rbx
0x140008532  call    WPP_SF_qqsD
0x140008537  mov     r9, rsi
0x14000853a  mov     r8, r14
0x14000853d  mov     rdx, rdi
0x140008540  mov     ecx, 63307366h
0x140008545  call    USBSTOR_LogEntry
0x14000854a  mov     rcx, rbp
0x14000854d  call    USBSTOR_IsDeviceAsyncCapable
0x140008552  test    al, al
0x140008554  jz      short loc_140008561
0x140008556  mov     rdx, rbp; Context
0x140008559  mov     rcx, rdi; Object
0x14000855c  call    USBSTOR_QueueAsyncNotification
0x140008561  mov     rcx, rdi; DeviceObject
0x140008564  call    UsbStorStartNextPacket
0x140008569  mov     rcx, rbx; Irp
0x14000856c  call    cs:__imp_PoStartNextPowerIrp
0x140008573  nop     dword ptr [rax+rax+00h]
0x140008578  mov     eax, esi
0x14000857a  add     rsp, 40h
0x14000857e  pop     r14
0x140008580  pop     rdi
0x140008581  pop     rsi
0x140008582  pop     rbp
0x140008583  pop     rbx
0x140008584  retn
```
