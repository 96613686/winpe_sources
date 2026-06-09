# std::current_exception(void)

- ea: `0x18002a1fc`
- end: `0x18002a22c`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002a5a0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002a21d`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002a21d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002a214`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002a214`

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
0x18002a1fc  push    rbx
0x18002a1fe  sub     rsp, 20h
0x18002a202  mov     rbx, rcx
0x18002a205  mov     qword ptr [rcx], 0
0x18002a20c  mov     qword ptr [rcx+8], 0
0x18002a214  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002a21a  mov     rcx, rbx
0x18002a21d  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18002a223  mov     rax, rbx
0x18002a226  add     rsp, 20h
0x18002a22a  pop     rbx
0x18002a22b  retn
```
