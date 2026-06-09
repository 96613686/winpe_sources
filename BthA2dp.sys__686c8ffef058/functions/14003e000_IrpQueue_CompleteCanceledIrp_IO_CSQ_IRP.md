# IrpQueue::CompleteCanceledIrp(_IO_CSQ *,_IRP *)

- ea: `0x14003e000`
- end: `0x14003e022`
- name: `?CompleteCanceledIrp@IrpQueue@@CAXPEAU_IO_CSQ@@PEAU_IRP@@@Z`
- size: `34`
- prototype: `IO_CSQ_COMPLETE_CANCELED_IRP`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14003e010`
- `ntoskrnl!IofCompleteRequest` at `0x14003e010`

## pseudocode

```c
void __fastcall IrpQueue::CompleteCanceledIrp(PIO_CSQ Csq, PIRP Irp)
{
  Irp->IoStatus.Status = -1073741536;
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x14003e000  sub     rsp, 28h
0x14003e004  mov     rcx, rdx; Irp
0x14003e007  mov     dword ptr [rdx+30h], 0C0000120h
0x14003e00e  xor     edx, edx; PriorityBoost
0x14003e010  call    cs:__imp_IofCompleteRequest
0x14003e017  nop     dword ptr [rax+rax+00h]
0x14003e01c  add     rsp, 28h
0x14003e020  retn
```
