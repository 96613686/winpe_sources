# std::make_exception_ptr<std::future_error>(std::future_error)

- ea: `0x18003b3b8`
- end: `0x18003b40b`
- name: `??$make_exception_ptr@Vfuture_error@std@@@std@@YA?AVexception_ptr@0@Vfuture_error@0@@Z`
- size: `83`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d5a4`

## callees

- `0x18002d092`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x18003b3e4`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x18003b3e4`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003b3d1`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18003b3d1`

## pseudocode

```c
_QWORD *__fastcall std::make_exception_ptr<std::future_error>(_QWORD *a1, _QWORD *a2)
{
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCreate(a1);
  __ExceptionPtrCopyException(a1, a2, &TI3_AVfuture_error_std__);
  *a2 = &std::exception::`vftable';
  o___std_exception_destroy_0(a2 + 1);
  return a1;
}

```

## disassembly

```asm
0x18003b3b8  mov     [rsp+arg_8], rbx
0x18003b3bd  push    rdi
0x18003b3be  sub     rsp, 20h
0x18003b3c2  xor     eax, eax
0x18003b3c4  mov     rbx, rdx
0x18003b3c7  mov     [rcx], rax
0x18003b3ca  mov     rdi, rcx
0x18003b3cd  mov     [rcx+8], rax
0x18003b3d1  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18003b3d7  lea     r8, _TI3?AVfuture_error@std@@; throw info for 'class std::future_error'
0x18003b3de  mov     rdx, rbx
0x18003b3e1  mov     rcx, rdi
0x18003b3e4  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x18003b3ea  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18003b3f1  lea     rcx, [rbx+8]
0x18003b3f5  mov     [rbx], rax
0x18003b3f8  call    _o___std_exception_destroy_0
0x18003b3fd  mov     rbx, [rsp+28h+arg_8]
0x18003b402  mov     rax, rdi
0x18003b405  add     rsp, 20h
0x18003b409  pop     rdi
0x18003b40a  retn
```
