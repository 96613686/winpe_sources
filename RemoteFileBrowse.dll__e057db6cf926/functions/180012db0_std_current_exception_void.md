# std::current_exception(void)

- ea: `0x180012db0`
- end: `0x180012de0`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001854d`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180012dc8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180012dc8`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180012dd1`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180012dd1`

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
0x180012db0  push    rbx
0x180012db2  sub     rsp, 20h
0x180012db6  mov     rbx, rcx
0x180012db9  mov     qword ptr [rcx], 0
0x180012dc0  mov     qword ptr [rcx+8], 0
0x180012dc8  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180012dce  mov     rcx, rbx
0x180012dd1  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180012dd7  mov     rax, rbx
0x180012dda  add     rsp, 20h
0x180012dde  pop     rbx
0x180012ddf  retn
```
