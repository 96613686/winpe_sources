# FreeNDFRepairVisitor::~FreeNDFRepairVisitor(void)

- ea: `0x18000c3b4`
- end: `0x18000c3bf`
- name: `??1FreeNDFRepairVisitor@@UEAA@XZ`
- size: `11`
- prototype: `void __fastcall(FreeNDFRepairVisitor *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180010f8a`
- `0x180010ffa`
- `0x18001100c`

## pseudocode

```c
void __fastcall FreeNDFRepairVisitor::~FreeNDFRepairVisitor(FreeNDFRepairVisitor *this)
{
  *(_QWORD *)this = &Visitor<tagRepairInfo *>::`vftable';
}

```

## disassembly

```asm
0x18000c3b4  lea     rax, ??_7?$Visitor@PEAUtagRepairInfo@@@@6B@; const Visitor<tagRepairInfo *>::`vftable'
0x18000c3bb  mov     [rcx], rax
0x18000c3be  retn
```
