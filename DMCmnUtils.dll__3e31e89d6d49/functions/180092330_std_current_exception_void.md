# std::current_exception(void)

- ea: `0x180092330`
- end: `0x18009236d`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `61`
- prototype: ``
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x1800b37f0`
- `0x1800b38c0`
- `0x1800b39b0`
- `0x1800b3a80`
- `0x1800b50b0`
- `0x1800b5240`
- `0x1800b6940`
- `0x1800b6a00`
- `0x1800b6b60`
- `0x1800b6be0`
- `0x1800b6c80`
- `0x1800b6d00`
- `0x1800b6d60`
- `0x1800b6e10`
- `0x1800b7070`
- `0x1800b7700`
- `0x1800b95a2`
- `0x1800b964e`
- `0x1800b96fa`
- `0x1800ba1a6`
- `0x1800ba1fe`
- `0x1800ba405`
- `0x1800ba491`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180092348`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180092348`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180092357`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180092357`

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
0x180092330  push    rbx
0x180092332  sub     rsp, 20h
0x180092336  mov     rbx, rcx
0x180092339  mov     qword ptr [rcx], 0
0x180092340  mov     qword ptr [rcx+8], 0
0x180092348  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18009234f  nop     dword ptr [rax+rax+00h]
0x180092354  mov     rcx, rbx
0x180092357  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18009235e  nop     dword ptr [rax+rax+00h]
0x180092363  mov     rax, rbx
0x180092366  add     rsp, 20h
0x18009236a  pop     rbx
0x18009236b  retn
```
