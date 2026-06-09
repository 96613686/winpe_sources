# MIDL_user_allocate

- ea: `0x180004dc0`
- end: `0x180004de3`
- name: `MIDL_user_allocate`
- size: `35`
- prototype: `void *__stdcall(size_t size)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180006a40`
- `0x180007170`
- `0x180007600`
- `0x180007810`
- `0x1800078a0`
- `0x1800079b0`
- `0x180007a50`
- `0x180007e10`
- `0x180007e8c`
- `0x180007f18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dc9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004ddc`

## pseudocode

```c
void *__stdcall MIDL_user_allocate(size_t size)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 0, size);
}

```

## disassembly

```asm
0x180004dc0  push    rbx
0x180004dc2  sub     rsp, 20h
0x180004dc6  mov     rbx, rcx
0x180004dc9  call    cs:__imp_GetProcessHeap
0x180004dcf  mov     r8, rbx
0x180004dd2  xor     edx, edx
0x180004dd4  mov     rcx, rax
0x180004dd7  add     rsp, 20h
0x180004ddb  pop     rbx
0x180004ddc  jmp     cs:__imp_HeapAlloc
```
