# std::make_exception_ptr<winrt::hresult_canceled>(winrt::hresult_canceled)

- ea: `0x18001e1f8`
- end: `0x18001e240`
- name: `??$make_exception_ptr@Uhresult_canceled@winrt@@@std@@YA?AVexception_ptr@0@Uhresult_canceled@winrt@@@Z`
- size: `72`
- prototype: `_QWORD *__fastcall(_QWORD *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800205dc`

## callees

- `0x180005e10`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001e211`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001e211`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x18001e224`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x18001e224`

## pseudocode

```c
_QWORD *__fastcall std::make_exception_ptr<winrt::hresult_canceled>(_QWORD *a1, void *a2)
{
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCreate(a1);
  __ExceptionPtrCopyException(a1, a2, &TI2_AUhresult_canceled_winrt__);
  winrt::hresult_error::~hresult_error((winrt::hresult_error *)a2);
  return a1;
}

```

## disassembly

```asm
0x18001e1f8  mov     [rsp+arg_8], rbx
0x18001e1fd  push    rdi
0x18001e1fe  sub     rsp, 20h
0x18001e202  xor     eax, eax
0x18001e204  mov     rbx, rdx
0x18001e207  mov     [rcx], rax
0x18001e20a  mov     rdi, rcx
0x18001e20d  mov     [rcx+8], rax
0x18001e211  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001e217  lea     r8, _TI2?AUhresult_canceled@winrt@@; throw info for 'struct winrt::hresult_canceled'
0x18001e21e  mov     rdx, rbx
0x18001e221  mov     rcx, rdi
0x18001e224  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x18001e22a  mov     rcx, rbx; this
0x18001e22d  call    ??1hresult_error@winrt@@QEAA@XZ; winrt::hresult_error::~hresult_error(void)
0x18001e232  mov     rbx, [rsp+28h+arg_8]
0x18001e237  mov     rax, rdi
0x18001e23a  add     rsp, 20h
0x18001e23e  pop     rdi
0x18001e23f  retn
```
