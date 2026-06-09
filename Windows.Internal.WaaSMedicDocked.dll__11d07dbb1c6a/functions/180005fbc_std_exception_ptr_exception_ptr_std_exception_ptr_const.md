# std::exception_ptr::exception_ptr(std::exception_ptr const &)

- ea: `0x180005fbc`
- end: `0x180005fe3`
- name: `??0exception_ptr@std@@QEAA@AEBV01@@Z`
- size: `39`
- prototype: `__int64 __fastcall(std::exception_ptr *__hidden this, const struct std::exception_ptr *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180007014`
- `0x180009bd4`
- `0x18000a034`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180005fd4`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180005fd4`

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
0x180005fbc  push    rbx
0x180005fbe  sub     rsp, 20h
0x180005fc2  mov     rbx, rcx
0x180005fc5  mov     qword ptr [rcx], 0
0x180005fcc  mov     qword ptr [rcx+8], 0
0x180005fd4  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180005fda  mov     rax, rbx
0x180005fdd  add     rsp, 20h
0x180005fe1  pop     rbx
0x180005fe2  retn
```
