# FMIFS_MESSAGE::FMIFS_MESSAGE(void)

- ea: `0x180003e60`
- end: `0x180003e9c`
- name: `??0FMIFS_MESSAGE@@QEAA@XZ`
- size: `60`
- prototype: `FMIFS_MESSAGE *__fastcall(FMIFS_MESSAGE *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004900`
- `0x180004ca0`
- `0x180005240`
- `0x1800058a0`
- `0x180008a88`
- `0x180008ba0`

## import_xrefs

- `ulib!?SetClassDescriptor@OBJECT@@IEAAXPEBVCLASS_DESCRIPTOR@@@Z` at `0x180003e83`
- `ulib!?SetClassDescriptor@OBJECT@@IEAAXPEBVCLASS_DESCRIPTOR@@@Z` at `0x180003e83`
- `ulib!??0MESSAGE@@QEAA@XZ` at `0x180003e69`
- `ulib!??0MESSAGE@@QEAA@XZ` at `0x180003e69`

## pseudocode

```c
FMIFS_MESSAGE *__fastcall FMIFS_MESSAGE::FMIFS_MESSAGE(FMIFS_MESSAGE *this)
{
  const struct CLASS_DESCRIPTOR *v2; // rdx

  MESSAGE::MESSAGE((MESSAGE *)this);
  v2 = (const struct CLASS_DESCRIPTOR *)FMIFS_MESSAGE_cd;
  *(_QWORD *)this = &FMIFS_MESSAGE::`vftable';
  OBJECT::SetClassDescriptor(this, v2);
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 15) = 0;
  return this;
}

```

## disassembly

```asm
0x180003e60  push    rbx
0x180003e62  sub     rsp, 20h
0x180003e66  mov     rbx, rcx
0x180003e69  call    cs:__imp_??0MESSAGE@@QEAA@XZ; MESSAGE::MESSAGE(void)
0x180003e6f  mov     rdx, cs:?FMIFS_MESSAGE_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const FMIFS_MESSAGE_cd
0x180003e76  lea     rax, ??_7FMIFS_MESSAGE@@6B@; const FMIFS_MESSAGE::`vftable'
0x180003e7d  mov     rcx, rbx
0x180003e80  mov     [rbx], rax
0x180003e83  call    cs:__imp_?SetClassDescriptor@OBJECT@@IEAAXPEBVCLASS_DESCRIPTOR@@@Z; OBJECT::SetClassDescriptor(CLASS_DESCRIPTOR const *)
0x180003e89  xor     eax, eax
0x180003e8b  mov     [rbx+68h], rax
0x180003e8f  mov     [rbx+78h], rax
0x180003e93  mov     rax, rbx
0x180003e96  add     rsp, 20h
0x180003e9a  pop     rbx
0x180003e9b  retn
```
