# AhcDriverDispatchCreate

- ea: `0x14002c7c0`
- end: `0x14002c7e4`
- name: `AhcDriverDispatchCreate`
- size: `36`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002c7d0`
- `ntoskrnl!IofCompleteRequest` at `0x14002c7d0`

## pseudocode

```c
__int64 __fastcall AhcDriverDispatchCreate(__int64 a1, IRP *a2)
{
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14002c7c0  sub     rsp, 28h
0x14002c7c4  mov     rcx, rdx; Irp
0x14002c7c7  mov     dword ptr [rdx+30h], 0
0x14002c7ce  xor     edx, edx; PriorityBoost
0x14002c7d0  call    cs:__imp_IofCompleteRequest
0x14002c7d7  nop     dword ptr [rax+rax+00h]
0x14002c7dc  xor     eax, eax
0x14002c7de  add     rsp, 28h
0x14002c7e2  retn
```
