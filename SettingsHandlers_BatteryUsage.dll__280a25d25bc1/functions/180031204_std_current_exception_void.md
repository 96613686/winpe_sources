# std::current_exception(void)

- ea: `0x180031204`
- end: `0x180031234`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180051244`
- `0x180057868`
- `0x180057a06`
- `0x180057d02`
- `0x180057ee0`
- `0x180057fab`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003121c`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003121c`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031225`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180031225`

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
0x180031204  push    rbx
0x180031206  sub     rsp, 20h
0x18003120a  mov     rbx, rcx
0x18003120d  mov     qword ptr [rcx], 0
0x180031214  mov     qword ptr [rcx+8], 0
0x18003121c  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180031222  mov     rcx, rbx
0x180031225  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18003122b  mov     rax, rbx
0x18003122e  add     rsp, 20h
0x180031232  pop     rbx
0x180031233  retn
```
