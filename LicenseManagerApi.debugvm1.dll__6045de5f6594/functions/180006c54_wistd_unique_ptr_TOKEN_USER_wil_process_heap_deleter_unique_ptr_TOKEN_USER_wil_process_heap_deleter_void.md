# wistd::unique_ptr<_TOKEN_USER,wil::process_heap_deleter>::~unique_ptr<_TOKEN_USER,wil::process_heap_deleter>(void)

- ea: `0x180006c54`
- end: `0x180006c83`
- name: `??1?$unique_ptr@U_TOKEN_USER@@Uprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800122a5`

## callees

- `0x180006c54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006c77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006c77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006c69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006c69`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_TOKEN_USER,wil::process_heap_deleter>::~unique_ptr<_TOKEN_USER,wil::process_heap_deleter>(
        void **a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x180006c54  push    rbx
0x180006c56  sub     rsp, 20h
0x180006c5a  mov     rbx, [rcx]
0x180006c5d  mov     qword ptr [rcx], 0
0x180006c64  test    rbx, rbx
0x180006c67  jz      short loc_180006C7D
0x180006c69  call    cs:__imp_GetProcessHeap
0x180006c6f  mov     r8, rbx; lpMem
0x180006c72  xor     edx, edx; dwFlags
0x180006c74  mov     rcx, rax; hHeap
0x180006c77  call    cs:__imp_HeapFree
0x180006c7d  add     rsp, 20h
0x180006c81  pop     rbx
0x180006c82  retn
```
