# std::exception_ptr::exception_ptr(std::exception_ptr const &)

- ea: `0x18000f6d0`
- end: `0x18000f6f7`
- name: `??0exception_ptr@std@@QEAA@AEBV01@@Z`
- size: `39`
- prototype: `std::exception_ptr *__fastcall(std::exception_ptr *this, const struct std::exception_ptr *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011f90`
- `0x180012704`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000f6e8`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18000f6e8`

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
0x18000f6d0  push    rbx
0x18000f6d2  sub     rsp, 20h
0x18000f6d6  mov     rbx, rcx
0x18000f6d9  mov     qword ptr [rcx], 0
0x18000f6e0  mov     qword ptr [rcx+8], 0
0x18000f6e8  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18000f6ee  mov     rax, rbx
0x18000f6f1  add     rsp, 20h
0x18000f6f5  pop     rbx
0x18000f6f6  retn
```
