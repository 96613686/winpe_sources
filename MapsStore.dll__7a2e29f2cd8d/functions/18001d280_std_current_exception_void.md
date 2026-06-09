# std::current_exception(void)

- ea: `0x18001d280`
- end: `0x18001d2b0`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18008e4c3`
- `0x18008e515`
- `0x18008e5a4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001d298`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001d298`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18001d2a1`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18001d2a1`

## pseudocode

```c
_QWORD *__fastcall std::current_exception(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCreate(a1);
  __ExceptionPtrCurrentException(a1);
  return a1;
}

```

## disassembly

```asm
0x18001d280  push    rbx
0x18001d282  sub     rsp, 20h
0x18001d286  mov     rbx, rcx
0x18001d289  mov     qword ptr [rcx], 0
0x18001d290  mov     qword ptr [rcx+8], 0
0x18001d298  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001d29e  mov     rcx, rbx
0x18001d2a1  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18001d2a7  mov     rax, rbx
0x18001d2aa  add     rsp, 20h
0x18001d2ae  pop     rbx
0x18001d2af  retn
```
