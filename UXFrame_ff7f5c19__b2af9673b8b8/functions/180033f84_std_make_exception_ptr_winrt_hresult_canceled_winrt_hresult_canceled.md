# std::make_exception_ptr<winrt::hresult_canceled>(winrt::hresult_canceled)

- ea: `0x180033f84`
- end: `0x180033fcc`
- name: `??$make_exception_ptr@Uhresult_canceled@winrt@@@std@@YA?AVexception_ptr@0@Uhresult_canceled@winrt@@@Z`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180034b9c`

## callees

- `0x180004208`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180033f9d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180033f9d`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180033fb0`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180033fb0`

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
0x180033f84  mov     [rsp+arg_10], rbx
0x180033f89  push    rdi
0x180033f8a  sub     rsp, 30h
0x180033f8e  xor     eax, eax
0x180033f90  mov     rbx, rdx
0x180033f93  mov     [rcx], rax
0x180033f96  mov     rdi, rcx
0x180033f99  mov     [rcx+8], rax
0x180033f9d  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180033fa3  lea     r8, _TI2?AUhresult_canceled@winrt@@; throw info for 'struct winrt::hresult_canceled'
0x180033faa  mov     rdx, rbx
0x180033fad  mov     rcx, rdi
0x180033fb0  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x180033fb6  mov     rcx, rbx; this
0x180033fb9  call    ??1hresult_error@winrt@@QEAA@XZ; winrt::hresult_error::~hresult_error(void)
0x180033fbe  mov     rbx, [rsp+38h+arg_10]
0x180033fc3  mov     rax, rdi
0x180033fc6  add     rsp, 30h
0x180033fca  pop     rdi
0x180033fcb  retn
```
