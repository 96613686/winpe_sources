# VEManagerDispatch(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180015ea0`
- end: `0x180015f59`
- name: `?VEManagerDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `185`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180012670`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180015f37`
- `ntoskrnl!IofCompleteRequest` at `0x180015f37`

## pseudocode

```c
__int64 __fastcall VEManagerDispatch(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  unsigned int LowPart; // ebp
  unsigned int Length; // ebx
  void *v6; // rsi
  unsigned int v7; // ebx
  unsigned int *v9; // [rsp+20h] [rbp-28h]
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v10 = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  Length = CurrentStackLocation->Parameters.Read.Length;
  LODWORD(CurrentStackLocation) = CurrentStackLocation->Parameters.Create.Options;
  v6 = *(struct _IRP **)((char *)&a2->AssociatedIrp.MasterIrp + ((LowPart & 3) != 0 ? 0x58 : 0));
  LogWrite(3, 0, L"VEManagerDispatch() - IOCTL %d received.", LowPart);
  LODWORD(v9) = DispatchIOCTL(LowPart, v6, (unsigned int)CurrentStackLocation, Length, &v10);
  v7 = (unsigned int)v9;
  LogWrite(3, 0, L"VEManagerDispatch() - IOCTL %d processes with result %d.", LowPart, v9);
  a2->IoStatus.Information = v10;
  a2->IoStatus.Status = v7;
  IofCompleteRequest(a2, 0);
  return v7;
}

```

## disassembly

```asm
0x180015ea0  mov     [rsp+arg_0], rbx
0x180015ea5  mov     [rsp+arg_10], rbp
0x180015eaa  push    rsi
0x180015eab  push    rdi
0x180015eac  push    r14
0x180015eae  sub     rsp, 30h
0x180015eb2  mov     rdi, [rdx+0B8h]
0x180015eb9  lea     r8, aVemanagerdispa; "VEManagerDispatch() - IOCTL %d received"...
0x180015ec0  mov     [rsp+48h+arg_8], 0
0x180015ec8  mov     r14, rdx
0x180015ecb  mov     ebp, [rdi+18h]
0x180015ece  mov     eax, ebp
0x180015ed0  mov     ebx, [rdi+8]
0x180015ed3  and     al, 3
0x180015ed5  mov     edi, [rdi+10h]
0x180015ed8  neg     al
0x180015eda  mov     r9d, ebp
0x180015edd  sbb     rax, rax
0x180015ee0  and     eax, 58h
0x180015ee3  mov     rsi, [rax+rdx+18h]
0x180015ee8  xor     edx, edx
0x180015eea  lea     ecx, [rdx+3]
0x180015eed  call    LogWrite
0x180015ef2  lea     rax, [rsp+48h+arg_8]
0x180015ef7  mov     r9d, ebx; unsigned int
0x180015efa  mov     r8d, edi; unsigned int
0x180015efd  mov     [rsp+48h+var_28], rax; unsigned int *
0x180015f02  mov     rdx, rsi; void *
0x180015f05  mov     ecx, ebp; unsigned int
0x180015f07  call    ?DispatchIOCTL@@YAJKPEAXKKPEAK@Z; DispatchIOCTL(ulong,void *,ulong,ulong,ulong *)
0x180015f0c  xor     edx, edx
0x180015f0e  mov     dword ptr [rsp+48h+var_28], eax
0x180015f12  mov     r9d, ebp
0x180015f15  lea     r8, aVemanagerdispa_0; "VEManagerDispatch() - IOCTL %d processe"...
0x180015f1c  mov     ebx, eax
0x180015f1e  lea     ecx, [rdx+3]
0x180015f21  call    LogWrite
0x180015f26  mov     ecx, [rsp+48h+arg_8]
0x180015f2a  xor     edx, edx; PriorityBoost
0x180015f2c  mov     [r14+38h], rcx
0x180015f30  mov     rcx, r14; Irp
0x180015f33  mov     [r14+30h], ebx
0x180015f37  call    cs:__imp_IofCompleteRequest
0x180015f3e  nop     dword ptr [rax+rax+00h]
0x180015f43  mov     rbp, [rsp+48h+arg_10]
0x180015f48  mov     eax, ebx
0x180015f4a  mov     rbx, [rsp+48h+arg_0]
0x180015f4f  add     rsp, 30h
0x180015f53  pop     r14
0x180015f55  pop     rdi
0x180015f56  pop     rsi
0x180015f57  retn
```
