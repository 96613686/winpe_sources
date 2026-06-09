# std::make_exception_ptr<winrt::hresult_canceled>(winrt::hresult_canceled)

- ea: `0x180024d54`
- end: `0x180024d9c`
- name: `??$make_exception_ptr@Uhresult_canceled@winrt@@@std@@YA?AVexception_ptr@0@Uhresult_canceled@winrt@@@Z`
- size: `72`
- prototype: `_QWORD *__fastcall(_QWORD *, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002586c`

## callees

- `0x18000a608`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180024d6d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180024d6d`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180024d80`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180024d80`

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
0x180024d54  mov     [rsp+arg_8], rbx
0x180024d59  push    rdi
0x180024d5a  sub     rsp, 20h
0x180024d5e  xor     eax, eax
0x180024d60  mov     rbx, rdx
0x180024d63  mov     [rcx], rax
0x180024d66  mov     rdi, rcx
0x180024d69  mov     [rcx+8], rax
0x180024d6d  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180024d73  lea     r8, _TI2?AUhresult_canceled@winrt@@; throw info for 'struct winrt::hresult_canceled'
0x180024d7a  mov     rdx, rbx
0x180024d7d  mov     rcx, rdi
0x180024d80  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x180024d86  mov     rcx, rbx; this
0x180024d89  call    ??1hresult_error@winrt@@QEAA@XZ; winrt::hresult_error::~hresult_error(void)
0x180024d8e  mov     rbx, [rsp+28h+arg_8]
0x180024d93  mov     rax, rdi
0x180024d96  add     rsp, 20h
0x180024d9a  pop     rdi
0x180024d9b  retn
```
