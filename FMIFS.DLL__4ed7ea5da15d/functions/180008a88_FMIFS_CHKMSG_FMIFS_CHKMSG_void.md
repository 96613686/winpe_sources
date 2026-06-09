# FMIFS_CHKMSG::FMIFS_CHKMSG(void)

- ea: `0x180008a88`
- end: `0x180008ab9`
- name: `??0FMIFS_CHKMSG@@QEAA@XZ`
- size: `49`
- prototype: `FMIFS_CHKMSG *__fastcall(FMIFS_CHKMSG *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007270`
- `0x180007610`
- `0x180008b00`

## callees

- `0x180003e60`

## import_xrefs

- `ulib!?SetClassDescriptor@OBJECT@@IEAAXPEBVCLASS_DESCRIPTOR@@@Z` at `0x180008aaa`
- `ulib!?SetClassDescriptor@OBJECT@@IEAAXPEBVCLASS_DESCRIPTOR@@@Z` at `0x180008aaa`

## pseudocode

```c
FMIFS_CHKMSG *__fastcall FMIFS_CHKMSG::FMIFS_CHKMSG(FMIFS_CHKMSG *this)
{
  const struct CLASS_DESCRIPTOR *v2; // rdx

  FMIFS_MESSAGE::FMIFS_MESSAGE(this);
  v2 = (const struct CLASS_DESCRIPTOR *)FMIFS_CHKMSG_cd;
  *(_QWORD *)this = &FMIFS_CHKMSG::`vftable';
  OBJECT::SetClassDescriptor(this, v2);
  return this;
}

```

## disassembly

```asm
0x180008a88  push    rbx
0x180008a8a  sub     rsp, 20h
0x180008a8e  mov     rbx, rcx
0x180008a91  call    ??0FMIFS_MESSAGE@@QEAA@XZ; FMIFS_MESSAGE::FMIFS_MESSAGE(void)
0x180008a96  mov     rdx, cs:?FMIFS_CHKMSG_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const FMIFS_CHKMSG_cd
0x180008a9d  lea     rax, ??_7FMIFS_CHKMSG@@6B@; const FMIFS_CHKMSG::`vftable'
0x180008aa4  mov     rcx, rbx
0x180008aa7  mov     [rbx], rax
0x180008aaa  call    cs:__imp_?SetClassDescriptor@OBJECT@@IEAAXPEBVCLASS_DESCRIPTOR@@@Z; OBJECT::SetClassDescriptor(CLASS_DESCRIPTOR const *)
0x180008ab0  mov     rax, rbx
0x180008ab3  add     rsp, 20h
0x180008ab7  pop     rbx
0x180008ab8  retn
```
