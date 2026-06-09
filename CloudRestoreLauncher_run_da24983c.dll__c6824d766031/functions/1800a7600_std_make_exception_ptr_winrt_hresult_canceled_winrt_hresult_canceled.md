# std::make_exception_ptr<winrt::hresult_canceled>(winrt::hresult_canceled)

- ea: `0x1800a7600`
- end: `0x1800a7648`
- name: `??$make_exception_ptr@Uhresult_canceled@winrt@@@std@@YA?AVexception_ptr@0@Uhresult_canceled@winrt@@@Z`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a8fdc`
- `0x1801068ac`

## callees

- `0x180016c60`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a7619`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800a7619`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x1800a762c`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x1800a762c`

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
0x1800a7600  mov     [rsp+arg_8], rbx
0x1800a7605  push    rdi
0x1800a7606  sub     rsp, 20h
0x1800a760a  xor     eax, eax
0x1800a760c  mov     rbx, rdx
0x1800a760f  mov     [rcx], rax
0x1800a7612  mov     rdi, rcx
0x1800a7615  mov     [rcx+8], rax
0x1800a7619  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800a761f  lea     r8, _TI2?AUhresult_canceled@winrt@@; throw info for 'struct winrt::hresult_canceled'
0x1800a7626  mov     rdx, rbx
0x1800a7629  mov     rcx, rdi
0x1800a762c  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800a7632  mov     rcx, rbx; this
0x1800a7635  call    ??1hresult_error@winrt@@QEAA@XZ; winrt::hresult_error::~hresult_error(void)
0x1800a763a  mov     rbx, [rsp+28h+arg_8]
0x1800a763f  mov     rax, rdi
0x1800a7642  add     rsp, 20h
0x1800a7646  pop     rdi
0x1800a7647  retn
```
