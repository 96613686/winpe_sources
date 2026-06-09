# std::make_exception_ptr<winrt::hresult_canceled>(winrt::hresult_canceled)

- ea: `0x180028bd8`
- end: `0x180028c20`
- name: `??$make_exception_ptr@Uhresult_canceled@winrt@@@std@@YA?AVexception_ptr@0@Uhresult_canceled@winrt@@@Z`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002929c`

## callees

- `0x1800078ec`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180028c04`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180028c04`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180028bf1`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180028bf1`

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
0x180028bd8  mov     [rsp+arg_8], rbx
0x180028bdd  push    rdi
0x180028bde  sub     rsp, 20h
0x180028be2  xor     eax, eax
0x180028be4  mov     rbx, rdx
0x180028be7  mov     [rcx], rax
0x180028bea  mov     rdi, rcx
0x180028bed  mov     [rcx+8], rax
0x180028bf1  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180028bf7  lea     r8, _TI2?AUhresult_canceled@winrt@@; throw info for 'struct winrt::hresult_canceled'
0x180028bfe  mov     rdx, rbx
0x180028c01  mov     rcx, rdi
0x180028c04  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x180028c0a  mov     rcx, rbx; this
0x180028c0d  call    ??1hresult_error@winrt@@QEAA@XZ; winrt::hresult_error::~hresult_error(void)
0x180028c12  mov     rbx, [rsp+28h+arg_8]
0x180028c17  mov     rax, rdi
0x180028c1a  add     rsp, 20h
0x180028c1e  pop     rdi
0x180028c1f  retn
```
