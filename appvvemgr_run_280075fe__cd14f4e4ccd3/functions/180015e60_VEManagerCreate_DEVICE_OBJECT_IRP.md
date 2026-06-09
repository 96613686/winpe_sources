# VEManagerCreate(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180015e60`
- end: `0x180015e8c`
- name: `?VEManagerCreate@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `44`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180015e78`
- `ntoskrnl!IofCompleteRequest` at `0x180015e78`

## pseudocode

```c
__int64 __fastcall VEManagerCreate(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x180015e60  sub     rsp, 28h
0x180015e64  mov     rcx, rdx; Irp
0x180015e67  mov     qword ptr [rdx+38h], 0
0x180015e6f  mov     dword ptr [rdx+30h], 0
0x180015e76  xor     edx, edx; PriorityBoost
0x180015e78  call    cs:__imp_IofCompleteRequest
0x180015e7f  nop     dword ptr [rax+rax+00h]
0x180015e84  xor     eax, eax
0x180015e86  add     rsp, 28h
0x180015e8a  retn
```
