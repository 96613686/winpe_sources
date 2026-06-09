# std::current_exception(void)

- ea: `0x1800f0830`
- end: `0x1800f0860`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x18015ce40`
- `0x18015d2b0`
- `0x18015d420`
- `0x18015d4d0`
- `0x180160e50`
- `0x180163a10`
- `0x180164550`
- `0x180164620`
- `0x1801656c0`
- `0x180165760`
- `0x180165860`
- `0x1801658e0`
- `0x180165960`
- `0x1801659c0`
- `0x180165a20`
- `0x180165ad0`
- `0x180165cb0`
- `0x1801661d0`
- `0x1801669f4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800f0851`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800f0851`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800f0848`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800f0848`

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
0x1800f0830  push    rbx
0x1800f0832  sub     rsp, 20h
0x1800f0836  mov     rbx, rcx
0x1800f0839  mov     qword ptr [rcx], 0
0x1800f0840  mov     qword ptr [rcx+8], 0
0x1800f0848  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800f084e  mov     rcx, rbx
0x1800f0851  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800f0857  mov     rax, rbx
0x1800f085a  add     rsp, 20h
0x1800f085e  pop     rbx
0x1800f085f  retn
```
