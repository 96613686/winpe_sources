# unknown_libname_9

- ea: `0x18000d5c0`
- end: `0x18000d5d8`
- name: `unknown_libname_9`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000ee80`

## import_xrefs

- `USER32!CopyRect` at `0x18000d5c9`
- `USER32!CopyRect` at `0x18000d5c9`

## pseudocode

```c
// Microsoft VisualC v7/14 64bit runtime
struct tagRECT *__fastcall unknown_libname_9(struct tagRECT *a1, const RECT *a2)
{
  CopyRect(a1, a2);
  return a1;
}

```

## disassembly

```asm
0x18000d5c0  push    rbx
0x18000d5c2  sub     rsp, 20h
0x18000d5c6  mov     rbx, rcx
0x18000d5c9  call    cs:CopyRect
0x18000d5cf  mov     rax, rbx
0x18000d5d2  add     rsp, 20h
0x18000d5d6  pop     rbx
0x18000d5d7  retn
```
