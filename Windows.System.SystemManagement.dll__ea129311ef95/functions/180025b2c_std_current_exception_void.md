# std::current_exception(void)

- ea: `0x180025b2c`
- end: `0x180025b5c`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800271d8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180025b44`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180025b44`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180025b4d`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180025b4d`

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
0x180025b2c  push    rbx
0x180025b2e  sub     rsp, 20h
0x180025b32  mov     rbx, rcx
0x180025b35  mov     qword ptr [rcx], 0
0x180025b3c  mov     qword ptr [rcx+8], 0
0x180025b44  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180025b4a  mov     rcx, rbx
0x180025b4d  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180025b53  mov     rax, rbx
0x180025b56  add     rsp, 20h
0x180025b5a  pop     rbx
0x180025b5b  retn
```
