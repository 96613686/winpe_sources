# FreeNDFRepairVisitor::FreeNDFRepairVisitor(void)

- ea: `0x18000c3a0`
- end: `0x18000c3ae`
- name: `??0FreeNDFRepairVisitor@@QEAA@XZ`
- size: `14`
- prototype: `FreeNDFRepairVisitor *__fastcall(FreeNDFRepairVisitor *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18001101e`

## pseudocode

```c
FreeNDFRepairVisitor *__fastcall FreeNDFRepairVisitor::FreeNDFRepairVisitor(FreeNDFRepairVisitor *this)
{
  *(_QWORD *)this = &FreeNDFRepairVisitor::`vftable';
  return this;
}

```

## disassembly

```asm
0x18000c3a0  lea     rax, ??_7FreeNDFRepairVisitor@@6B@; const FreeNDFRepairVisitor::`vftable'
0x18000c3a7  mov     [rcx], rax
0x18000c3aa  mov     rax, rcx
0x18000c3ad  retn
```
