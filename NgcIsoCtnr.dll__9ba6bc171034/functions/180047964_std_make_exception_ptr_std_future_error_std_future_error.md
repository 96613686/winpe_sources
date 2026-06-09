# std::make_exception_ptr<std::future_error>(std::future_error)

- ea: `0x180047964`
- end: `0x1800479b7`
- name: `??$make_exception_ptr@Vfuture_error@std@@@std@@YA?AVexception_ptr@0@Vfuture_error@0@@Z`
- size: `83`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180048170`

## callees

- `0x180008382`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004797d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004797d`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180047990`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180047990`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180047964  mov     [rsp+arg_8], rbx
0x180047969  push    rdi
0x18004796a  sub     rsp, 20h
0x18004796e  xor     eax, eax
0x180047970  mov     rbx, rdx
0x180047973  mov     [rcx], rax
0x180047976  mov     rdi, rcx
0x180047979  mov     [rcx+8], rax
0x18004797d  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180047983  lea     r8, _TI3?AVfuture_error@std@@; throw info for 'class std::future_error'
0x18004798a  mov     rdx, rbx
0x18004798d  mov     rcx, rdi
0x180047990  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x180047996  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18004799d  lea     rcx, [rbx+8]
0x1800479a1  mov     [rbx], rax
0x1800479a4  call    _o___std_exception_destroy_0
0x1800479a9  mov     rbx, [rsp+28h+arg_8]
0x1800479ae  mov     rax, rdi
0x1800479b1  add     rsp, 20h
0x1800479b5  pop     rdi
0x1800479b6  retn
```
