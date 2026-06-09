# std::current_exception(void)

- ea: `0x180048d1c`
- end: `0x180048d4c`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180059b2d`
- `0x180059bae`
- `0x180059dcf`
- `0x180059e45`
- `0x180059ec2`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180048d3d`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180048d3d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180048d34`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180048d34`

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
0x180048d1c  push    rbx
0x180048d1e  sub     rsp, 20h
0x180048d22  mov     rbx, rcx
0x180048d25  mov     qword ptr [rcx], 0
0x180048d2c  mov     qword ptr [rcx+8], 0
0x180048d34  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180048d3a  mov     rcx, rbx
0x180048d3d  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180048d43  mov     rax, rbx
0x180048d46  add     rsp, 20h
0x180048d4a  pop     rbx
0x180048d4b  retn
```
