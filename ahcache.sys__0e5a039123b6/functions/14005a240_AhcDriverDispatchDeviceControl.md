# AhcDriverDispatchDeviceControl

- ea: `0x14005a240`
- end: `0x14005a2fc`
- name: `AhcDriverDispatchDeviceControl`
- size: `188`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14003e364`
- `0x1400497bc`
- `0x14005a240`

## import_xrefs

- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005a272`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14005a272`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005a25c`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005a25c`
- `ntoskrnl!IofCompleteRequest` at `0x14005a2e2`
- `ntoskrnl!IofCompleteRequest` at `0x14005a2e2`

## pseudocode

```c
__int64 __fastcall AhcDriverDispatchDeviceControl(__int64 a1, IRP *a2)
{
  unsigned int v2; // ebx
  __int64 CurrentServerSilo; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r8
  unsigned int v6; // ebx
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  v2 = g_AhcacheSiloContextSlot;
  v8 = 0;
  CurrentServerSilo = PsGetCurrentServerSilo();
  PsGetPermanentSiloContext(CurrentServerSilo, v2, &v8);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  a2->IoStatus.Information = 0;
  if ( (unsigned __int8)(CurrentStackLocation->Parameters.Read.ByteOffset.LowPart >> 2) < 0xCu )
  {
    v6 = AhcDispatch(v8);
  }
  else
  {
    v6 = -1073741811;
    AslLogCallPrintf(1, "AhcDriverDispatchDeviceControl", 593, "Incorrect device control code [%x]", -1073741811);
  }
  a2->IoStatus.Status = v6;
  IofCompleteRequest(a2, 0);
  return v6;
}

```

## disassembly

```asm
0x14005a240  mov     [rsp+arg_0], rbx
0x14005a245  push    rdi
0x14005a246  sub     rsp, 30h
0x14005a24a  mov     ebx, cs:g_AhcacheSiloContextSlot
0x14005a250  mov     rdi, rdx
0x14005a253  mov     [rsp+38h+arg_8], 0
0x14005a25c  call    cs:__imp_PsGetCurrentServerSilo
0x14005a263  nop     dword ptr [rax+rax+00h]
0x14005a268  lea     r8, [rsp+38h+arg_8]
0x14005a26d  mov     edx, ebx
0x14005a26f  mov     rcx, rax
0x14005a272  call    cs:__imp_PsGetPermanentSiloContext
0x14005a279  nop     dword ptr [rax+rax+00h]
0x14005a27e  mov     r8, [rdi+0B8h]
0x14005a285  mov     qword ptr [rdi+38h], 0
0x14005a28d  mov     eax, [r8+18h]
0x14005a291  shr     eax, 2
0x14005a294  movzx   edx, al
0x14005a297  cmp     edx, 0Ch
0x14005a29a  jb      short loc_14005A2C5
0x14005a29c  mov     ebx, 0C000000Dh
0x14005a2a1  lea     r9, aIncorrectDevic; "Incorrect device control code [%x]"
0x14005a2a8  mov     r8d, 251h
0x14005a2ae  mov     [rsp+38h+var_18], ebx
0x14005a2b2  lea     rdx, aAhcdriverdispa_0; "AhcDriverDispatchDeviceControl"
0x14005a2b9  mov     ecx, 1
0x14005a2be  call    AslLogCallPrintf
0x14005a2c3  jmp     short loc_14005A2DA
0x14005a2c5  movzx   r9d, byte ptr [rdi+40h]
0x14005a2ca  mov     r8, [r8+20h]
0x14005a2ce  mov     rcx, [rsp+38h+arg_8]
0x14005a2d3  call    AhcDispatch
0x14005a2d8  mov     ebx, eax
0x14005a2da  xor     edx, edx; PriorityBoost
0x14005a2dc  mov     [rdi+30h], ebx
0x14005a2df  mov     rcx, rdi; Irp
0x14005a2e2  call    cs:__imp_IofCompleteRequest
0x14005a2e9  nop     dword ptr [rax+rax+00h]
0x14005a2ee  mov     eax, ebx
0x14005a2f0  mov     rbx, [rsp+38h+arg_0]
0x14005a2f5  add     rsp, 30h
0x14005a2f9  pop     rdi
0x14005a2fa  retn
```
