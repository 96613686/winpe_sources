# std::current_exception(void)

- ea: `0x18001af94`
- end: `0x18001afc4`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180042a24`
- `0x180042e24`
- `0x18004310e`
- `0x180043184`
- `0x18004322d`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18001afb5`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18001afb5`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001afac`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18001afac`

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
0x18001af94  push    rbx
0x18001af96  sub     rsp, 20h
0x18001af9a  mov     rbx, rcx
0x18001af9d  mov     qword ptr [rcx], 0
0x18001afa4  mov     qword ptr [rcx+8], 0
0x18001afac  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18001afb2  mov     rcx, rbx
0x18001afb5  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18001afbb  mov     rax, rbx
0x18001afbe  add     rsp, 20h
0x18001afc2  pop     rbx
0x18001afc3  retn
```
