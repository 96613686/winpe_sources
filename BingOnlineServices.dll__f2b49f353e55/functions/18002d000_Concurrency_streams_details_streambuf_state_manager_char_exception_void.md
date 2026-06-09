# Concurrency::streams::details::streambuf_state_manager<char>::exception(void)

- ea: `0x18002d000`
- end: `0x18002d02e`
- name: `?exception@?$streambuf_state_manager@D@details@streams@Concurrency@@UEBA?AVexception_ptr@std@@XZ`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002d01f`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002d01f`

## pseudocode

```c
_QWORD *__fastcall Concurrency::streams::details::streambuf_state_manager<char>::exception(__int64 a1, _QWORD *a2)
{
  *a2 = 0;
  a2[1] = 0;
  __ExceptionPtrCopy(a2, (const void *)(a1 + 24));
  return a2;
}

```

## disassembly

```asm
0x18002d000  push    rbx
0x18002d002  sub     rsp, 20h
0x18002d006  mov     rbx, rdx
0x18002d009  mov     qword ptr [rdx], 0
0x18002d010  mov     qword ptr [rdx+8], 0
0x18002d018  lea     rdx, [rcx+18h]
0x18002d01c  mov     rcx, rbx
0x18002d01f  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002d025  mov     rax, rbx
0x18002d028  add     rsp, 20h
0x18002d02c  pop     rbx
0x18002d02d  retn
```
