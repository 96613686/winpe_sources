# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x18001b5e0`
- end: `0x18001b60f`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800289c8`

## callees

- `0x18001b5e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b603`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b603`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b5f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b5f5`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
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
0x18001b5e0  push    rbx
0x18001b5e2  sub     rsp, 20h
0x18001b5e6  mov     rbx, [rcx]
0x18001b5e9  mov     qword ptr [rcx], 0
0x18001b5f0  test    rbx, rbx
0x18001b5f3  jz      short loc_18001B609
0x18001b5f5  call    cs:__imp_GetProcessHeap
0x18001b5fb  mov     r8, rbx; lpMem
0x18001b5fe  xor     edx, edx; dwFlags
0x18001b600  mov     rcx, rax; hHeap
0x18001b603  call    cs:__imp_HeapFree
0x18001b609  add     rsp, 20h
0x18001b60d  pop     rbx
0x18001b60e  retn
```
