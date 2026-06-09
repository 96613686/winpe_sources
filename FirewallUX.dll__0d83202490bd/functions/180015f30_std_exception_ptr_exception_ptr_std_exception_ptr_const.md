# std::exception_ptr::exception_ptr(std::exception_ptr const &)

- ea: `0x180015f30`
- end: `0x180015f57`
- name: `??0exception_ptr@std@@QEAA@AEBV01@@Z`
- size: `39`
- prototype: `std::exception_ptr *__fastcall(std::exception_ptr *this, const struct std::exception_ptr *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800193c0`
- `0x180019b28`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180015f48`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180015f48`

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
0x180015f30  push    rbx
0x180015f32  sub     rsp, 20h
0x180015f36  mov     rbx, rcx
0x180015f39  mov     qword ptr [rcx], 0
0x180015f40  mov     qword ptr [rcx+8], 0
0x180015f48  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180015f4e  mov     rax, rbx
0x180015f51  add     rsp, 20h
0x180015f55  pop     rbx
0x180015f56  retn
```
