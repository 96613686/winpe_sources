# std::exception_ptr::exception_ptr(std::exception_ptr const &)

- ea: `0x180046c44`
- end: `0x180046c6b`
- name: `??0exception_ptr@std@@QEAA@AEBV01@@Z`
- size: `39`
- prototype: `std::exception_ptr *__fastcall(std::exception_ptr *this, const struct std::exception_ptr *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800484d0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180046c5c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180046c5c`

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
0x180046c44  push    rbx
0x180046c46  sub     rsp, 20h
0x180046c4a  mov     rbx, rcx
0x180046c4d  mov     qword ptr [rcx], 0
0x180046c54  mov     qword ptr [rcx+8], 0
0x180046c5c  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180046c62  mov     rax, rbx
0x180046c65  add     rsp, 20h
0x180046c69  pop     rbx
0x180046c6a  retn
```
