# std::exception_ptr::_Copy_exception(void *,void const *)

- ea: `0x18003567c`
- end: `0x1800356d0`
- name: `?_Copy_exception@exception_ptr@std@@SA?AV12@PEAXPEBX@Z`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180032c78`
- `0x180034598`
- `0x18004716c`

## callees

- `0x18003567c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x1800356b7`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x1800356b7`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800356a3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800356a3`

## pseudocode

```c
_QWORD *__fastcall std::exception_ptr::_Copy_exception(_QWORD *a1, const void *a2, const void *a3)
{
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCreate(a1);
  if ( a3 )
    __ExceptionPtrCopyException(a1, a2, a3);
  return a1;
}

```

## disassembly

```asm
0x18003567c  mov     [rsp+arg_8], rbx
0x180035681  mov     [rsp+arg_10], rsi
0x180035686  push    rdi
0x180035687  sub     rsp, 20h
0x18003568b  mov     rdi, r8
0x18003568e  mov     qword ptr [rcx], 0
0x180035695  mov     rsi, rdx
0x180035698  mov     qword ptr [rcx+8], 0
0x1800356a0  mov     rbx, rcx
0x1800356a3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800356a9  test    rdi, rdi
0x1800356ac  jz      short loc_1800356BD
0x1800356ae  mov     r8, rdi
0x1800356b1  mov     rdx, rsi
0x1800356b4  mov     rcx, rbx
0x1800356b7  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x1800356bd  mov     rsi, [rsp+28h+arg_10]
0x1800356c2  mov     rax, rbx
0x1800356c5  mov     rbx, [rsp+28h+arg_8]
0x1800356ca  add     rsp, 20h
0x1800356ce  pop     rdi
0x1800356cf  retn
```
