# std::exception_ptr::exception_ptr(std::exception_ptr const &)

- ea: `0x1800346b0`
- end: `0x1800346d7`
- name: `??0exception_ptr@std@@QEAA@AEBV01@@Z`
- size: `39`
- prototype: `__int64 __fastcall(std::exception_ptr *__hidden this, const struct std::exception_ptr *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180036ec4`
- `0x180036f1c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800346c8`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800346c8`

## pseudocode

```c
std::exception_ptr *__fastcall std::exception_ptr::exception_ptr(
        std::exception_ptr *this,
        const struct std::exception_ptr *a2)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  __ExceptionPtrCopy(this, a2);
  return this;
}

```

## disassembly

```asm
0x1800346b0  push    rbx
0x1800346b2  sub     rsp, 20h
0x1800346b6  mov     rbx, rcx
0x1800346b9  mov     qword ptr [rcx], 0
0x1800346c0  mov     qword ptr [rcx+8], 0
0x1800346c8  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800346ce  mov     rax, rbx
0x1800346d1  add     rsp, 20h
0x1800346d5  pop     rbx
0x1800346d6  retn
```
