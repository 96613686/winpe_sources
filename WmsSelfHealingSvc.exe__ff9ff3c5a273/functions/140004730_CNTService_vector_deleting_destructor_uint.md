# CNTService::`vector deleting destructor'(uint)

- ea: `0x140004730`
- end: `0x140004756`
- name: `??_ECNTService@@UEAAPEAXI@Z`
- size: `38`
- prototype: `CNTService *__fastcall(CNTService *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x1400011d4`
- `0x140004730`

## pseudocode

```c
CNTService *__fastcall CNTService::`vector deleting destructor'(CNTService *this, char a2)
{
  *(_QWORD *)this = &CNTService::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140004730  push    rbx
0x140004732  sub     rsp, 20h
0x140004736  lea     rax, ??_7CNTService@@6B@; const CNTService::`vftable'
0x14000473d  mov     rbx, rcx
0x140004740  mov     [rcx], rax
0x140004743  test    dl, 1
0x140004746  jz      short loc_14000474D
0x140004748  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000474d  mov     rax, rbx
0x140004750  add     rsp, 20h
0x140004754  pop     rbx
0x140004755  retn
```
