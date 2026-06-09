# USBSTOR_FdoSetPowerCompletion

- ea: `0x14000fc80`
- end: `0x14000fd6d`
- name: `USBSTOR_FdoSetPowerCompletion`
- size: `237`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003630`
- `0x14000fc80`

## import_xrefs

- `ntoskrnl!PoCallDriver` at `0x14000fd3d`
- `ntoskrnl!PoCallDriver` at `0x14000fd3d`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x14000fcc4`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x14000fcc4`
- `ntoskrnl!IofCompleteRequest` at `0x14000fd50`
- `ntoskrnl!IofCompleteRequest` at `0x14000fd50`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000fcea`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000fcea`

## pseudocode

```c
void __fastcall USBSTOR_FdoSetPowerCompletion(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        _QWORD *Context)
{
  __int64 v4; // rbx
  IRP *v6; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax

  v4 = Context[8];
  if ( PowerState.SystemState == PowerSystemWorking )
  {
    if ( *(_QWORD *)(v4 + 1968) )
    {
      USBSTOR_LogEntry(1919973478, v4, 0, 0);
      PoFxReportDevicePoweredOn(*(_QWORD *)(v4 + 1968));
    }
  }
  else
  {
    v6 = *(IRP **)(v4 + 160);
    *(_QWORD *)(v4 + 160) = 0;
    PoStartNextPowerIrp(v6);
    if ( (Context[6] & 0x2000) != 0 )
    {
      CurrentStackLocation = v6->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
      *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                 + 6);
      CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
      CurrentStackLocation[-1].Control = 0;
      v6->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      PoCallDriver(*(PDEVICE_OBJECT *)(v4 + 24), v6);
    }
    else
    {
      IofCompleteRequest(v6, 0);
    }
  }
}

```

## disassembly

```asm
0x14000fc80  mov     [rsp+arg_0], rbx
0x14000fc85  mov     [rsp+arg_8], rsi
0x14000fc8a  push    rdi
0x14000fc8b  sub     rsp, 20h
0x14000fc8f  mov     rbx, [r9+40h]
0x14000fc93  mov     rsi, r9
0x14000fc96  cmp     r8d, 1
0x14000fc9a  jnz     short loc_14000FCD5
0x14000fc9c  cmp     qword ptr [rbx+7B0h], 0
0x14000fca4  jz      loc_14000FD5C
0x14000fcaa  xor     r9d, r9d
0x14000fcad  xor     r8d, r8d
0x14000fcb0  mov     rdx, rbx
0x14000fcb3  mov     ecx, 72707866h
0x14000fcb8  call    USBSTOR_LogEntry
0x14000fcbd  mov     rcx, [rbx+7B0h]
0x14000fcc4  call    cs:__imp_PoFxReportDevicePoweredOn
0x14000fccb  nop     dword ptr [rax+rax+00h]
0x14000fcd0  jmp     loc_14000FD5C
0x14000fcd5  mov     rdi, [rbx+0A0h]
0x14000fcdc  mov     rcx, rdi; Irp
0x14000fcdf  mov     qword ptr [rbx+0A0h], 0
0x14000fcea  call    cs:__imp_PoStartNextPowerIrp
0x14000fcf1  nop     dword ptr [rax+rax+00h]
0x14000fcf6  test    dword ptr [rsi+30h], 2000h
0x14000fcfd  jz      short loc_14000FD4B
0x14000fcff  mov     rax, [rdi+0B8h]
0x14000fd06  mov     rdx, rdi; Irp
0x14000fd09  movups  xmm0, xmmword ptr [rax]
0x14000fd0c  movups  xmmword ptr [rax-48h], xmm0
0x14000fd10  movups  xmm1, xmmword ptr [rax+10h]
0x14000fd14  movups  xmmword ptr [rax-38h], xmm1
0x14000fd18  movups  xmm0, xmmword ptr [rax+20h]
0x14000fd1c  movups  xmmword ptr [rax-28h], xmm0
0x14000fd20  movsd   xmm1, qword ptr [rax+30h]
0x14000fd25  movsd   qword ptr [rax-18h], xmm1
0x14000fd2a  mov     byte ptr [rax-45h], 0
0x14000fd2e  mov     rax, [rdi+0B8h]
0x14000fd35  or      byte ptr [rax+3], 1
0x14000fd39  mov     rcx, [rbx+18h]; DeviceObject
0x14000fd3d  call    cs:__imp_PoCallDriver
0x14000fd44  nop     dword ptr [rax+rax+00h]
0x14000fd49  jmp     short loc_14000FD5C
0x14000fd4b  xor     edx, edx; PriorityBoost
0x14000fd4d  mov     rcx, rdi; Irp
0x14000fd50  call    cs:__imp_IofCompleteRequest
0x14000fd57  nop     dword ptr [rax+rax+00h]
0x14000fd5c  mov     rbx, [rsp+28h+arg_0]
0x14000fd61  mov     rsi, [rsp+28h+arg_8]
0x14000fd66  add     rsp, 20h
0x14000fd6a  pop     rdi
0x14000fd6b  retn
```
