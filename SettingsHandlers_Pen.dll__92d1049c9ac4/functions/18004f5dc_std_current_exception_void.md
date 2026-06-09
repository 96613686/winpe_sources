# std::current_exception(void)

- ea: `0x18004f5dc`
- end: `0x18004f60c`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18005af56`
- `0x18005b46c`
- `0x18005b504`
- `0x18005b587`
- `0x18005b60a`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18004f5fd`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18004f5fd`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004f5f4`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004f5f4`

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
0x18004f5dc  push    rbx
0x18004f5de  sub     rsp, 20h
0x18004f5e2  mov     rbx, rcx
0x18004f5e5  mov     qword ptr [rcx], 0
0x18004f5ec  mov     qword ptr [rcx+8], 0
0x18004f5f4  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18004f5fa  mov     rcx, rbx
0x18004f5fd  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18004f603  mov     rax, rbx
0x18004f606  add     rsp, 20h
0x18004f60a  pop     rbx
0x18004f60b  retn
```
