# std::current_exception(void)

- ea: `0x180015978`
- end: `0x1800159a8`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x18005a11a`
- `0x18005a16c`
- `0x18005a1e9`
- `0x18005ae1d`
- `0x18005aecb`
- `0x18005afd4`
- `0x18005b0cb`
- `0x18005b77b`
- `0x18005bba6`
- `0x18005bc06`
- `0x18005bca0`
- `0x18005be70`
- `0x18005bf7f`
- `0x18005c1c7`
- `0x18005c751`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180015999`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180015999`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180015990`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180015990`

## pseudocode

```c
_QWORD *__fastcall std::current_exception(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCreate(a1);
  __ExceptionPtrCurrentException(a1);
  return a1;
}

```

## disassembly

```asm
0x180015978  push    rbx
0x18001597a  sub     rsp, 20h
0x18001597e  mov     rbx, rcx
0x180015981  mov     qword ptr [rcx], 0
0x180015988  mov     qword ptr [rcx+8], 0
0x180015990  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180015996  mov     rcx, rbx
0x180015999  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18001599f  mov     rax, rbx
0x1800159a2  add     rsp, 20h
0x1800159a6  pop     rbx
0x1800159a7  retn
```
