# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x18001071c`
- end: `0x18001074b`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001800b`

## callees

- `0x18001071c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001073f`
- `KERNEL32!HeapFree` at `0x18001073f`
- `KERNEL32!GetProcessHeap` at `0x180010731`
- `KERNEL32!GetProcessHeap` at `0x180010731`

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
0x18001071c  push    rbx
0x18001071e  sub     rsp, 20h
0x180010722  mov     rbx, [rcx]
0x180010725  mov     qword ptr [rcx], 0
0x18001072c  test    rbx, rbx
0x18001072f  jz      short loc_180010745
0x180010731  call    cs:__imp_GetProcessHeap
0x180010737  mov     r8, rbx; lpMem
0x18001073a  xor     edx, edx; dwFlags
0x18001073c  mov     rcx, rax; hHeap
0x18001073f  call    cs:__imp_HeapFree
0x180010745  add     rsp, 20h
0x180010749  pop     rbx
0x18001074a  retn
```
