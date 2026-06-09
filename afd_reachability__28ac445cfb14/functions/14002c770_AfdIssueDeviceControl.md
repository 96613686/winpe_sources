# AfdIssueDeviceControl

- ea: `0x14002c770`
- end: `0x14002c9c3`
- name: `AfdIssueDeviceControl`
- size: `595`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, void *Src, size_t Size, PVOID VirtualAddress, ULONG Length, char)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001c9ac`
- `0x140020970`
- `0x14002c3e0`
- `0x14002c728`
- `0x140037624`
- `0x140039198`
- `0x14003ce70`
- `0x14004f3e0`
- `0x1400627a0`

## callees

- `0x14002c770`
- `0x14002fd5c`
- `0x140072800`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14002c7bf`
- `ntoskrnl!KeInitializeEvent` at `0x14002c7bf`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c8ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002c8ee`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14002c81a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14002c81a`
- `ntoskrnl!KeReadStateEvent` at `0x14002c8a1`
- `ntoskrnl!KeReadStateEvent` at `0x14002c8a1`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002c7ce`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002c7ce`
- `ntoskrnl!IoFreeMdl` at `0x14002c95f`
- `ntoskrnl!IoFreeMdl` at `0x14002c986`
- `ntoskrnl!IoFreeMdl` at `0x14002c95f`
- `ntoskrnl!IoFreeMdl` at `0x14002c986`
- `ntoskrnl!MmUnlockPages` at `0x14002c977`
- `ntoskrnl!MmUnlockPages` at `0x14002c977`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002c946`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002c946`
- `ntoskrnl!IoAllocateMdl` at `0x14002c91f`
- `ntoskrnl!IoAllocateMdl` at `0x14002c91f`
- `ntoskrnl!IofCallDriver` at `0x14002c87b`
- `ntoskrnl!IofCallDriver` at `0x14002c87b`

## pseudocode

```c
__int64 __fastcall AfdIssueDeviceControl(
        PFILE_OBJECT FileObject,
        void *Src,
        size_t Size,
        PVOID VirtualAddress,
        ULONG Length,
        UCHAR a6)
{
  size_t v7; // r15
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rsi
  struct _MDL *v11; // rdi
  PIRP v12; // rax
  IRP *v13; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v15; // rax
  NTSTATUS v16; // eax
  NTSTATUS v17; // edi
  struct _MDL *Mdl; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-50h] BYREF
  struct _KEVENT Event; // [rsp+68h] [rbp-40h] BYREF

  v7 = (unsigned int)Size;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
  if ( VirtualAddress )
  {
    Mdl = IoAllocateMdl(VirtualAddress, Length, 0, 0, 0);
    v11 = Mdl;
    if ( !Mdl )
      return 3221225626LL;
    MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
  }
  else
  {
    v11 = 0;
  }
  v12 = IoBuildDeviceIoControlRequest(3u, RelatedDeviceObject, 0, 0, 0, 0, 1u, &Event, &IoStatusBlock);
  v13 = v12;
  if ( !v12 )
  {
    if ( v11 )
    {
      MmUnlockPages(v11);
      IoFreeMdl(v11);
    }
    return 3221225626LL;
  }
  v12->MdlAddress = v11;
  CurrentStackLocation = v12->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].MinorFunction = a6;
  CurrentStackLocation[-1].FileObject = FileObject;
  memmove(&CurrentStackLocation[-1].Parameters, Src, v7);
  v15 = v13->Tail.Overlay.CurrentStackLocation;
  v15[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)AfdRestartDeviceControl;
  v15[-1].Context = 0;
  v15[-1].Control = -32;
  v16 = IofCallDriver(RelatedDeviceObject, v13);
  v17 = v16;
  if ( v16 == 259 )
  {
    v17 = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  }
  else if ( (v16 & 0xC0000000) != 0xC0000000 && !KeReadStateEvent(&Event) )
  {
    if ( (byte_1400875CA & 0x40) != 0 )
      WPP_SF_q(278, 22, WPP_f5726d6c7e42399356e7224fda59383d_Traceguids, v13);
    __debugbreak();
  }
  if ( v17 >= 0 )
    return (unsigned int)IoStatusBlock.Status;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14002c770  mov     [rsp+arg_0], rbx
0x14002c775  mov     [rsp+arg_8], rsi
0x14002c77a  push    rdi
0x14002c77b  push    r12
0x14002c77d  push    r13
0x14002c77f  push    r14
0x14002c781  push    r15
0x14002c783  sub     rsp, 80h
0x14002c78a  mov     rbx, r9
0x14002c78d  mov     r15d, r8d
0x14002c790  mov     r12, rdx
0x14002c793  mov     r14, rcx
0x14002c796  xor     r13d, r13d
0x14002c799  mov     [rsp+0A8h+var_58], r13d
0x14002c79e  xorps   xmm0, xmm0
0x14002c7a1  xor     eax, eax
0x14002c7a3  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x14002c7a8  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14002c7ad  movups  xmmword ptr [rsp+0A8h+var_50], xmm0
0x14002c7b2  xor     r8d, r8d; State
0x14002c7b5  mov     edx, 1; Type
0x14002c7ba  lea     rcx, [rsp+0A8h+Event]; Event
0x14002c7bf  call    cs:__imp_KeInitializeEvent
0x14002c7c6  nop     dword ptr [rax+rax+00h]
0x14002c7cb  mov     rcx, r14; FileObject
0x14002c7ce  call    cs:__imp_IoGetRelatedDeviceObject
0x14002c7d5  nop     dword ptr [rax+rax+00h]
0x14002c7da  mov     rsi, rax
0x14002c7dd  test    rbx, rbx
0x14002c7e0  jnz     loc_14002C90A
0x14002c7e6  mov     edi, r13d
0x14002c7e9  lea     rax, [rsp+0A8h+var_50]
0x14002c7ee  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x14002c7f3  lea     rax, [rsp+0A8h+Event]
0x14002c7f8  mov     [rsp+0A8h+var_70], rax; Event
0x14002c7fd  mov     [rsp+0A8h+InternalDeviceIoControl], 1; InternalDeviceIoControl
0x14002c802  mov     [rsp+0A8h+OutputBufferLength], r13d; OutputBufferLength
0x14002c807  mov     [rsp+0A8h+OutputBuffer], r13; OutputBuffer
0x14002c80c  xor     r9d, r9d; InputBufferLength
0x14002c80f  xor     r8d, r8d; InputBuffer
0x14002c812  mov     rdx, rsi; DeviceObject
0x14002c815  mov     ecx, 3; IoControlCode
0x14002c81a  call    cs:__imp_IoBuildDeviceIoControlRequest
0x14002c821  nop     dword ptr [rax+rax+00h]
0x14002c826  mov     rbx, rax
0x14002c829  test    rax, rax
0x14002c82c  jz      loc_14002C8FE
0x14002c832  mov     [rax+8], rdi
0x14002c836  mov     rcx, [rax+0B8h]
0x14002c83d  movzx   eax, [rsp+0A8h+arg_28]
0x14002c845  mov     [rcx-47h], al
0x14002c848  mov     [rcx-18h], r14
0x14002c84c  mov     r8, r15; Size
0x14002c84f  add     rcx, 0FFFFFFFFFFFFFFC0h; void *
0x14002c853  mov     rdx, r12; Src
0x14002c856  call    memmove
0x14002c85b  mov     rax, [rbx+0B8h]
0x14002c862  lea     rcx, AfdRestartDeviceControl
0x14002c869  mov     [rax-10h], rcx
0x14002c86d  mov     [rax-8], r13
0x14002c871  mov     byte ptr [rax-45h], 0E0h
0x14002c875  mov     rdx, rbx; Irp
0x14002c878  mov     rcx, rsi; DeviceObject
0x14002c87b  call    cs:__imp_IofCallDriver
0x14002c882  nop     dword ptr [rax+rax+00h]
0x14002c887  mov     edi, eax
0x14002c889  cmp     eax, 103h
0x14002c88e  jz      short loc_14002C8DC
0x14002c890  and     eax, 0C0000000h
0x14002c895  cmp     eax, 0C0000000h
0x14002c89a  jz      short loc_14002C8B5
0x14002c89c  lea     rcx, [rsp+0A8h+Event]; Event
0x14002c8a1  call    cs:__imp_KeReadStateEvent
0x14002c8a8  nop     dword ptr [rax+rax+00h]
0x14002c8ad  test    eax, eax
0x14002c8af  jz      loc_14002C997
0x14002c8b5  test    edi, edi
0x14002c8b7  cmovns  edi, dword ptr [rsp+0A8h+var_50]
0x14002c8bc  mov     eax, edi
0x14002c8be  lea     r11, [rsp+0A8h+var_28]
0x14002c8c6  mov     rbx, [r11+30h]
0x14002c8ca  mov     rsi, [r11+38h]
0x14002c8ce  mov     rsp, r11
0x14002c8d1  pop     r15
0x14002c8d3  pop     r14
0x14002c8d5  pop     r13
0x14002c8d7  pop     r12
0x14002c8d9  pop     rdi
0x14002c8da  retn
0x14002c8dc  mov     [rsp+0A8h+OutputBuffer], r13; Timeout
0x14002c8e1  xor     r9d, r9d; Alertable
0x14002c8e4  xor     r8d, r8d; WaitMode
0x14002c8e7  xor     edx, edx; WaitReason
0x14002c8e9  lea     rcx, [rsp+0A8h+Event]; Object
0x14002c8ee  call    cs:__imp_KeWaitForSingleObject
0x14002c8f5  nop     dword ptr [rax+rax+00h]
0x14002c8fa  mov     edi, eax
0x14002c8fc  jmp     short loc_14002C8B5
0x14002c8fe  test    rdi, rdi
0x14002c901  jnz     short loc_14002C974
0x14002c903  mov     eax, 0C000009Ah
0x14002c908  jmp     short loc_14002C8BE
0x14002c90a  mov     [rsp+0A8h+OutputBuffer], r13; Irp
0x14002c90f  xor     r9d, r9d; ChargeQuota
0x14002c912  xor     r8d, r8d; SecondaryBuffer
0x14002c915  mov     edx, [rsp+0A8h+Length]; Length
0x14002c91c  mov     rcx, rbx; VirtualAddress
0x14002c91f  call    cs:__imp_IoAllocateMdl
0x14002c926  nop     dword ptr [rax+rax+00h]
0x14002c92b  mov     rdi, rax
0x14002c92e  mov     [rsp+0A8h+Mdl], rax
0x14002c936  test    rax, rax
0x14002c939  jz      short loc_14002C903
0x14002c93b  xor     edx, edx; AccessMode
0x14002c93d  mov     r8d, 1; Operation
0x14002c943  mov     rcx, rax; MemoryDescriptorList
0x14002c946  call    cs:__imp_MmProbeAndLockPages
0x14002c94d  nop     dword ptr [rax+rax+00h]
0x14002c952  jmp     loc_14002C7E9
0x14002c957  mov     rcx, [rsp+0A8h+Mdl]; Mdl
0x14002c95f  call    cs:__imp_IoFreeMdl
0x14002c966  nop     dword ptr [rax+rax+00h]
0x14002c96b  mov     eax, [rsp+0A8h+var_58]
0x14002c96f  jmp     loc_14002C8BE
0x14002c974  mov     rcx, rdi; MemoryDescriptorList
0x14002c977  call    cs:__imp_MmUnlockPages
0x14002c97e  nop     dword ptr [rax+rax+00h]
0x14002c983  mov     rcx, rdi; Mdl
0x14002c986  call    cs:__imp_IoFreeMdl
0x14002c98d  nop     dword ptr [rax+rax+00h]
0x14002c992  jmp     loc_14002C903
0x14002c997  test    cs:byte_1400875CA, 40h
0x14002c99e  jz      loc_140078CFA
0x14002c9a4  mov     edx, 16h
0x14002c9a9  mov     ecx, 116h
0x14002c9ae  mov     r9, rbx
0x14002c9b1  lea     r8, WPP_f5726d6c7e42399356e7224fda59383d_Traceguids
0x14002c9b8  call    WPP_SF_q
0x14002c9bd  nop
0x14002c9be  jmp     loc_140078CFA
0x1400737c0  push    rbp
0x1400737c2  sub     rsp, 50h
0x1400737c6  mov     rbp, rdx
0x1400737c9  mov     r8, rcx
0x1400737cc  lea     r9, [rbp+50h]
0x1400737d0  mov     edx, 0F71h
0x1400737d5  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x1400737dc  call    AfdExceptionFilter
0x1400737e1  nop
0x1400737e2  add     rsp, 50h
0x1400737e6  pop     rbp
0x1400737e7  retn
0x140078cfa  int     3; Trap to Debugger
0x140078cfb  jmp     loc_14002C8B5
```
