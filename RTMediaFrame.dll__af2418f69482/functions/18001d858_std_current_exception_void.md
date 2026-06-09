# std::current_exception(void)

- ea: `0x18001d858`
- end: `0x18001d888`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18004f6a0`
- `0x18004f879`
- `0x180050257`
- `0x1800506ac`
- `0x1800507d9`
- `0x180050e74`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18001d879`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18001d879`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001d870`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001d870`

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
0x18001d858  push    rbx
0x18001d85a  sub     rsp, 20h
0x18001d85e  mov     rbx, rcx
0x18001d861  mov     qword ptr [rcx], 0
0x18001d868  mov     qword ptr [rcx+8], 0
0x18001d870  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001d876  mov     rcx, rbx
0x18001d879  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18001d87f  mov     rax, rbx
0x18001d882  add     rsp, 20h
0x18001d886  pop     rbx
0x18001d887  retn
```
