# std::current_exception(void)

- ea: `0x1800245d0`
- end: `0x180024600`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180026a2f`
- `0x180026b09`
- `0x180026d3c`
- `0x180026db2`
- `0x180026e2f`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800245e8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800245e8`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800245f1`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800245f1`

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
0x1800245d0  push    rbx
0x1800245d2  sub     rsp, 20h
0x1800245d6  mov     rbx, rcx
0x1800245d9  mov     qword ptr [rcx], 0
0x1800245e0  mov     qword ptr [rcx+8], 0
0x1800245e8  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800245ee  mov     rcx, rbx
0x1800245f1  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800245f7  mov     rax, rbx
0x1800245fa  add     rsp, 20h
0x1800245fe  pop     rbx
0x1800245ff  retn
```
