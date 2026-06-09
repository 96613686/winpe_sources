# std::current_exception(void)

- ea: `0x1800277b8`
- end: `0x1800277e8`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180028178`
- `0x180028204`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800277d0`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800277d0`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800277d9`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800277d9`

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
0x1800277b8  push    rbx
0x1800277ba  sub     rsp, 20h
0x1800277be  mov     rbx, rcx
0x1800277c1  mov     qword ptr [rcx], 0
0x1800277c8  mov     qword ptr [rcx+8], 0
0x1800277d0  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800277d6  mov     rcx, rbx
0x1800277d9  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800277df  mov     rax, rbx
0x1800277e2  add     rsp, 20h
0x1800277e6  pop     rbx
0x1800277e7  retn
```
