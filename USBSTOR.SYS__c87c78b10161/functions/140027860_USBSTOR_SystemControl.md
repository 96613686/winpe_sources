# USBSTOR_SystemControl

- ea: `0x140027860`
- end: `0x1400279b7`
- name: `USBSTOR_SystemControl`
- size: `343`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140027860`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14002793c`
- `ntoskrnl!IofCallDriver` at `0x14002793c`
- `ntoskrnl!IofCompleteRequest` at `0x140027951`
- `ntoskrnl!IofCompleteRequest` at `0x140027951`
- `WMILIB!WmiSystemControl` at `0x14002790c`
- `WMILIB!WmiSystemControl` at `0x14002790c`

## pseudocode

```c
__int64 __fastcall USBSTOR_SystemControl(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  _QWORD *DeviceExtension; // rax
  char *v6; // rsi
  NTSTATUS v7; // edi
  _SYSCTL_IRP_DISPOSITION IrpDisposition; // [rsp+40h] [rbp+8h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  IrpDisposition = IrpProcessed;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1129535827, DeviceObject, Irp, CurrentStackLocation->MinorFunction);
  DeviceExtension = DeviceObject->DeviceExtension;
  if ( *(_DWORD *)DeviceExtension == 558842960 )
  {
    v6 = *(char **)(DeviceExtension[2] + 64LL);
  }
  else
  {
    v6 = 0;
    if ( *(_DWORD *)DeviceExtension == 558842950 )
      v6 = (char *)DeviceObject->DeviceExtension;
  }
  v7 = WmiSystemControl((PWMILIB_CONTEXT)(v6 + 1976), DeviceObject, Irp, &IrpDisposition);
  if ( IrpDisposition )
  {
    if ( IrpDisposition == IrpNotCompleted )
    {
      IofCompleteRequest(Irp, 0);
    }
    else
    {
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      v7 = IofCallDriver(*((PDEVICE_OBJECT *)v6 + 3), Irp);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1668512115, v7, 0, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140027860  mov     [rsp+arg_8], rbx
0x140027865  mov     [rsp+arg_10], rbp
0x14002786a  push    rsi
0x14002786b  push    rdi
0x14002786c  push    r14
0x14002786e  sub     rsp, 20h
0x140027872  mov     rdi, [rdx+0B8h]
0x140027879  mov     rbx, rdx
0x14002787c  mov     rbp, rcx
0x14002787f  mov     [rsp+38h+IrpDisposition], 0
0x140027887  mov     rcx, cs:WPP_GLOBAL_Control
0x14002788e  lea     r14, WPP_GLOBAL_Control
0x140027895  cmp     rcx, r14
0x140027898  jz      short loc_1400278C1
0x14002789a  mov     eax, [rcx+2Ch]
0x14002789d  test    al, 10h
0x14002789f  jz      short loc_1400278C1
0x1400278a1  cmp     byte ptr [rcx+29h], 4
0x1400278a5  jb      short loc_1400278C1
0x1400278a7  movzx   r9d, byte ptr [rdi+1]
0x1400278ac  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400278b3  mov     rcx, [rcx+18h]
0x1400278b7  mov     edx, 30h ; '0'
0x1400278bc  call    WPP_SF_d
0x1400278c1  movzx   r9d, byte ptr [rdi+1]
0x1400278c6  mov     r8, rbx
0x1400278c9  mov     rdx, rbp
0x1400278cc  mov     ecx, 43535953h
0x1400278d1  call    USBSTOR_LogEntry
0x1400278d6  mov     rax, [rbp+40h]
0x1400278da  mov     ecx, [rax]
0x1400278dc  cmp     ecx, 214F4450h
0x1400278e2  jnz     short loc_1400278EE
0x1400278e4  mov     rax, [rax+10h]
0x1400278e8  mov     rsi, [rax+40h]
0x1400278ec  jmp     short loc_1400278FA
0x1400278ee  xor     esi, esi
0x1400278f0  cmp     ecx, 214F4446h
0x1400278f6  cmovz   rsi, rax
0x1400278fa  lea     rcx, [rsi+7B8h]; WmiLibInfo
0x140027901  mov     r8, rbx; Irp
0x140027904  lea     r9, [rsp+38h+IrpDisposition]; IrpDisposition
0x140027909  mov     rdx, rbp; DeviceObject
0x14002790c  call    cs:__imp_WmiSystemControl
0x140027913  nop     dword ptr [rax+rax+00h]
0x140027918  mov     edx, [rsp+38h+IrpDisposition]
0x14002791c  mov     edi, eax
0x14002791e  test    edx, edx
0x140027920  jz      short loc_14002795D
0x140027922  sub     edx, 1
0x140027925  jz      short loc_14002794C
0x140027927  inc     byte ptr [rbx+43h]
0x14002792a  sub     edx, 1
0x14002792d  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140027935  mov     rdx, rbx; Irp
0x140027938  mov     rcx, [rsi+18h]; DeviceObject
0x14002793c  call    cs:__imp_IofCallDriver
0x140027943  nop     dword ptr [rax+rax+00h]
0x140027948  mov     edi, eax
0x14002794a  jmp     short loc_14002795D
0x14002794c  xor     edx, edx; PriorityBoost
0x14002794e  mov     rcx, rbx; Irp
0x140027951  call    cs:__imp_IofCompleteRequest
0x140027958  nop     dword ptr [rax+rax+00h]
0x14002795d  mov     rcx, cs:WPP_GLOBAL_Control
0x140027964  cmp     rcx, r14
0x140027967  jz      short loc_14002798E
0x140027969  mov     eax, [rcx+2Ch]
0x14002796c  test    al, 10h
0x14002796e  jz      short loc_14002798E
0x140027970  cmp     byte ptr [rcx+29h], 4
0x140027974  jb      short loc_14002798E
0x140027976  mov     rcx, [rcx+18h]
0x14002797a  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140027981  mov     edx, 31h ; '1'
0x140027986  mov     r9d, edi
0x140027989  call    WPP_SF_d
0x14002798e  movsxd  rdx, edi
0x140027991  xor     r9d, r9d
0x140027994  xor     r8d, r8d
0x140027997  mov     ecx, 63737973h
0x14002799c  call    USBSTOR_LogEntry
0x1400279a1  mov     rbx, [rsp+38h+arg_8]
0x1400279a6  mov     eax, edi
0x1400279a8  mov     rbp, [rsp+38h+arg_10]
0x1400279ad  add     rsp, 20h
0x1400279b1  pop     r14
0x1400279b3  pop     rdi
0x1400279b4  pop     rsi
0x1400279b5  retn
```
