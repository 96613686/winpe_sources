# USBSTOR_PdoSetPowerCompletion

- ea: `0x14000ec40`
- end: `0x14000ed09`
- name: `USBSTOR_PdoSetPowerCompletion`
- size: `201`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003630`
- `0x14000ec40`
- `0x140010eb8`
- `0x140012c8c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000ecf3`
- `ntoskrnl!IofCompleteRequest` at `0x14000ecf3`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000ece2`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000ece2`

## pseudocode

```c
void __fastcall USBSTOR_PdoSetPowerCompletion(
        PDEVICE_OBJECT DeviceObject,
        __int64 MinorFunction,
        POWER_STATE PowerState,
        PVOID Context,
        PIO_STATUS_BLOCK IoStatus)
{
  PVOID DeviceExtension; // rax
  IRP *v7; // rbx
  __int64 LowPart; // rsi
  __int64 Status; // rbp
  __int64 v10; // rax
  __int64 v11; // r8

  DeviceExtension = DeviceObject->DeviceExtension;
  v7 = (IRP *)*((_QWORD *)DeviceExtension + 7);
  *((_QWORD *)DeviceExtension + 7) = 0;
  LowPart = (int)v7->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  Status = IoStatus->Status;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v10 = PowerSystemStateString((unsigned int)LowPart, MinorFunction, WPP_GLOBAL_Control, Context);
    WPP_SF_qqsD(*(_QWORD *)(v11 + 24), 47, v11, (_DWORD)DeviceObject, (char)v7, v10, Status);
  }
  USBSTOR_LogEntry(1668313968, DeviceObject, LowPart, Status);
  v7->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  v7->IoStatus.Status = 0;
  PoStartNextPowerIrp(v7);
  IofCompleteRequest(v7, 0);
}

```

## disassembly

```asm
0x14000ec40  push    rbx
0x14000ec42  push    rbp
0x14000ec43  push    rsi
0x14000ec44  push    rdi
0x14000ec45  sub     rsp, 48h
0x14000ec49  mov     rax, [rcx+40h]
0x14000ec4d  mov     rdi, rcx
0x14000ec50  mov     rbx, [rax+38h]
0x14000ec54  mov     qword ptr [rax+38h], 0
0x14000ec5c  mov     rax, [rbx+0B8h]
0x14000ec63  movsxd  rsi, dword ptr [rax+18h]
0x14000ec67  mov     rax, [rsp+68h+IoStatus]
0x14000ec6f  movsxd  rbp, dword ptr [rax]
0x14000ec72  mov     r8, cs:WPP_GLOBAL_Control
0x14000ec79  lea     rax, WPP_GLOBAL_Control
0x14000ec80  cmp     r8, rax
0x14000ec83  jz      short loc_14000ECBA
0x14000ec85  mov     eax, [r8+2Ch]
0x14000ec89  test    al, 4
0x14000ec8b  jz      short loc_14000ECBA
0x14000ec8d  cmp     byte ptr [r8+29h], 4
0x14000ec92  jb      short loc_14000ECBA
0x14000ec94  mov     ecx, esi
0x14000ec96  call    PowerSystemStateString
0x14000ec9b  mov     rcx, [r8+18h]
0x14000ec9f  mov     edx, 2Fh ; '/'
0x14000eca4  mov     [rsp+68h+var_38], ebp
0x14000eca8  mov     r9, rdi
0x14000ecab  mov     [rsp+68h+var_40], rax
0x14000ecb0  mov     [rsp+68h+var_48], rbx
0x14000ecb5  call    WPP_SF_qqsD
0x14000ecba  mov     r9, rbp
0x14000ecbd  mov     r8, rsi
0x14000ecc0  mov     rdx, rdi
0x14000ecc3  mov     ecx, 63707370h
0x14000ecc8  call    USBSTOR_LogEntry
0x14000eccd  mov     rax, [rbx+0B8h]
0x14000ecd4  mov     rcx, rbx; Irp
0x14000ecd7  or      byte ptr [rax+3], 1
0x14000ecdb  mov     dword ptr [rbx+30h], 0
0x14000ece2  call    cs:__imp_PoStartNextPowerIrp
0x14000ece9  nop     dword ptr [rax+rax+00h]
0x14000ecee  xor     edx, edx; PriorityBoost
0x14000ecf0  mov     rcx, rbx; Irp
0x14000ecf3  call    cs:__imp_IofCompleteRequest
0x14000ecfa  nop     dword ptr [rax+rax+00h]
0x14000ecff  add     rsp, 48h
0x14000ed03  pop     rdi
0x14000ed04  pop     rsi
0x14000ed05  pop     rbp
0x14000ed06  pop     rbx
0x14000ed07  retn
```
