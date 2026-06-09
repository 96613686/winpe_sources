# std::current_exception(void)

- ea: `0x18003a88c`
- end: `0x18003a8bc`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18006c1fe`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003a8a4`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003a8a4`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18003a8ad`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18003a8ad`

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
0x18003a88c  push    rbx
0x18003a88e  sub     rsp, 20h
0x18003a892  mov     rbx, rcx
0x18003a895  mov     qword ptr [rcx], 0
0x18003a89c  mov     qword ptr [rcx+8], 0
0x18003a8a4  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003a8aa  mov     rcx, rbx
0x18003a8ad  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18003a8b3  mov     rax, rbx
0x18003a8b6  add     rsp, 20h
0x18003a8ba  pop     rbx
0x18003a8bb  retn
```
