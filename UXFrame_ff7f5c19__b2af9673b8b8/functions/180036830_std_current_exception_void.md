# std::current_exception(void)

- ea: `0x180036830`
- end: `0x180036860`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180036f1c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180036848`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180036848`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180036851`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180036851`

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
0x180036830  push    rbx
0x180036832  sub     rsp, 20h
0x180036836  mov     rbx, rcx
0x180036839  mov     qword ptr [rcx], 0
0x180036840  mov     qword ptr [rcx+8], 0
0x180036848  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003684e  mov     rcx, rbx
0x180036851  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180036857  mov     rax, rbx
0x18003685a  add     rsp, 20h
0x18003685e  pop     rbx
0x18003685f  retn
```
