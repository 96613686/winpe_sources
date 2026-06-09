# std::make_exception_ptr<std::future_error>(std::future_error)

- ea: `0x180004ca0`
- end: `0x180004cf3`
- name: `??$make_exception_ptr@Vfuture_error@std@@@std@@YA?AVexception_ptr@0@Vfuture_error@0@@Z`
- size: `83`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005688`

## callees

- `0x18000355e`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180004ccc`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180004ccc`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180004cb9`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180004cb9`

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
0x180004ca0  mov     [rsp+arg_8], rbx
0x180004ca5  push    rdi
0x180004ca6  sub     rsp, 20h
0x180004caa  xor     eax, eax
0x180004cac  mov     rbx, rdx
0x180004caf  mov     [rcx], rax
0x180004cb2  mov     rdi, rcx
0x180004cb5  mov     [rcx+8], rax
0x180004cb9  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180004cbf  lea     r8, _TI3?AVfuture_error@std@@; throw info for 'class std::future_error'
0x180004cc6  mov     rdx, rbx
0x180004cc9  mov     rcx, rdi
0x180004ccc  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x180004cd2  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180004cd9  lea     rcx, [rbx+8]
0x180004cdd  mov     [rbx], rax
0x180004ce0  call    _o___std_exception_destroy_0
0x180004ce5  mov     rbx, [rsp+28h+arg_8]
0x180004cea  mov     rax, rdi
0x180004ced  add     rsp, 20h
0x180004cf1  pop     rdi
0x180004cf2  retn
```
