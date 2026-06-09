# std::current_exception(void)

- ea: `0x18001ef6c`
- end: `0x18001ef9c`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800412bb`
- `0x18004161a`
- `0x180041806`
- `0x18004187c`
- `0x1800418f9`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001ef84`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001ef84`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18001ef8d`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18001ef8d`

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
0x18001ef6c  push    rbx
0x18001ef6e  sub     rsp, 20h
0x18001ef72  mov     rbx, rcx
0x18001ef75  mov     qword ptr [rcx], 0
0x18001ef7c  mov     qword ptr [rcx+8], 0
0x18001ef84  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001ef8a  mov     rcx, rbx
0x18001ef8d  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18001ef93  mov     rax, rbx
0x18001ef96  add     rsp, 20h
0x18001ef9a  pop     rbx
0x18001ef9b  retn
```
