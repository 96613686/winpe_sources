# IrpQueue::CompleteAllRequests(long)

- ea: `0x140012b28`
- end: `0x140012b6f`
- name: `?CompleteAllRequests@IrpQueue@@QEAAXJ@Z`
- size: `71`
- prototype: `void __fastcall(PIO_CSQ Csq, int)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140015060`
- `0x14001ee94`
- `0x140020960`
- `0x14002fa70`
- `0x140030980`
- `0x1400329ec`
- `0x14003d690`
- `0x14003d7b0`

## callees

- `0x140012b28`

## import_xrefs

- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140012b52`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x140012b52`
- `ntoskrnl!IofCompleteRequest` at `0x140012b41`
- `ntoskrnl!IofCompleteRequest` at `0x140012b41`

## pseudocode

```c
void __fastcall IrpQueue::CompleteAllRequests(PIO_CSQ Csq, NTSTATUS a2)
{
  struct _IO_CSQ *i; // rbx
  PIRP v4; // rax

  for ( i = Csq; ; Csq = i )
  {
    v4 = IoCsqRemoveNextIrp(Csq, 0);
    if ( !v4 )
      break;
    v4->IoStatus.Status = a2;
    IofCompleteRequest(v4, 8);
  }
}

```

## disassembly

```asm
0x140012b28  mov     [rsp+arg_0], rbx
0x140012b2d  push    rdi
0x140012b2e  sub     rsp, 20h
0x140012b32  mov     edi, edx
0x140012b34  mov     rbx, rcx
0x140012b37  jmp     short loc_140012B50
0x140012b39  mov     dl, 8; PriorityBoost
0x140012b3b  mov     [rax+30h], edi
0x140012b3e  mov     rcx, rax; Irp
0x140012b41  call    cs:__imp_IofCompleteRequest
0x140012b48  nop     dword ptr [rax+rax+00h]
0x140012b4d  mov     rcx, rbx; Csq
0x140012b50  xor     edx, edx; PeekContext
0x140012b52  call    cs:__imp_IoCsqRemoveNextIrp
0x140012b59  nop     dword ptr [rax+rax+00h]
0x140012b5e  test    rax, rax
0x140012b61  jnz     short loc_140012B39
0x140012b63  mov     rbx, [rsp+28h+arg_0]
0x140012b68  add     rsp, 20h
0x140012b6c  pop     rdi
0x140012b6d  retn
```
