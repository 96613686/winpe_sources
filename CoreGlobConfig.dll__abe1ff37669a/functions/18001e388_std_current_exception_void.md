# std::current_exception(void)

- ea: `0x18001e388`
- end: `0x18001e3b8`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180023ad8`
- `0x1800241a0`
- `0x1800241f2`
- `0x180024293`
- `0x180024316`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001e3a0`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001e3a0`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18001e3a9`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18001e3a9`

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
0x18001e388  push    rbx
0x18001e38a  sub     rsp, 20h
0x18001e38e  mov     rbx, rcx
0x18001e391  mov     qword ptr [rcx], 0
0x18001e398  mov     qword ptr [rcx+8], 0
0x18001e3a0  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001e3a6  mov     rcx, rbx
0x18001e3a9  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18001e3af  mov     rax, rbx
0x18001e3b2  add     rsp, 20h
0x18001e3b6  pop     rbx
0x18001e3b7  retn
```
