# std::rethrow_exception(std::exception_ptr)

- ea: `0x180009bbc`
- end: `0x180009bcc`
- name: `?rethrow_exception@std@@YAXVexception_ptr@1@@Z`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180007014`
- `0x180009bd4`
- `0x18000a034`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180009bc5`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180009bc5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn std::rethrow_exception(const void *a1)
{
  __ExceptionPtrRethrow(a1);
  JUMPOUT(0x180009BCBLL);
}

```

## disassembly

```asm
0x180009bbc  mov     [rsp+arg_0], rcx
0x180009bc1  sub     rsp, 28h
0x180009bc5  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
