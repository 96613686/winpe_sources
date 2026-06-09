# std::make_exception_ptr<std::future_error>(std::future_error)

- ea: `0x18001820c`
- end: `0x18001825f`
- name: `??$make_exception_ptr@Vfuture_error@std@@@std@@YA?AVexception_ptr@0@Vfuture_error@0@@Z`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180018b48`
- `0x180036f94`

## callees

- `0x1800040d2`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180018225`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180018225`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180018238`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180018238`

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
0x18001820c  mov     [rsp+arg_8], rbx
0x180018211  push    rdi
0x180018212  sub     rsp, 20h
0x180018216  xor     eax, eax
0x180018218  mov     rbx, rdx
0x18001821b  mov     [rcx], rax
0x18001821e  mov     rdi, rcx
0x180018221  mov     [rcx+8], rax
0x180018225  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001822b  lea     r8, _TI3?AVfuture_error@std@@; throw info for 'class std::future_error'
0x180018232  mov     rdx, rbx
0x180018235  mov     rcx, rdi
0x180018238  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x18001823e  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180018245  lea     rcx, [rbx+8]
0x180018249  mov     [rbx], rax
0x18001824c  call    _o___std_exception_destroy_0
0x180018251  mov     rbx, [rsp+28h+arg_8]
0x180018256  mov     rax, rdi
0x180018259  add     rsp, 20h
0x18001825d  pop     rdi
0x18001825e  retn
```
