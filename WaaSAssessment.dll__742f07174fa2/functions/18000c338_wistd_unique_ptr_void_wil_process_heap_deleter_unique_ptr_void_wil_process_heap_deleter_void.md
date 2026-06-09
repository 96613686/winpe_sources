# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x18000c338`
- end: `0x18000c367`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180019d3e`

## callees

- `0x18000c338`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c34d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c34d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c35b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c35b`

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
0x18000c338  push    rbx
0x18000c33a  sub     rsp, 20h
0x18000c33e  mov     rbx, [rcx]
0x18000c341  mov     qword ptr [rcx], 0
0x18000c348  test    rbx, rbx
0x18000c34b  jz      short loc_18000C361
0x18000c34d  call    cs:__imp_GetProcessHeap
0x18000c353  mov     r8, rbx; lpMem
0x18000c356  xor     edx, edx; dwFlags
0x18000c358  mov     rcx, rax; hHeap
0x18000c35b  call    cs:__imp_HeapFree
0x18000c361  add     rsp, 20h
0x18000c365  pop     rbx
0x18000c366  retn
```
