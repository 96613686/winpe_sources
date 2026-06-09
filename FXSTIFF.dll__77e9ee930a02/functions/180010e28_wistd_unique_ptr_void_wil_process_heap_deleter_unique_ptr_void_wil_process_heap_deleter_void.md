# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180010e28`
- end: `0x180010e64`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018ddb`

## callees

- `0x180010e28`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180010e51`
- `KERNEL32!HeapFree` at `0x180010e51`
- `KERNEL32!GetProcessHeap` at `0x180010e3d`
- `KERNEL32!GetProcessHeap` at `0x180010e3d`

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
0x180010e28  push    rbx
0x180010e2a  sub     rsp, 20h
0x180010e2e  mov     rbx, [rcx]
0x180010e31  mov     qword ptr [rcx], 0
0x180010e38  test    rbx, rbx
0x180010e3b  jz      short loc_180010E5D
0x180010e3d  call    cs:__imp_GetProcessHeap
0x180010e44  nop     dword ptr [rax+rax+00h]
0x180010e49  mov     r8, rbx; lpMem
0x180010e4c  xor     edx, edx; dwFlags
0x180010e4e  mov     rcx, rax; hHeap
0x180010e51  call    cs:__imp_HeapFree
0x180010e58  nop     dword ptr [rax+rax+00h]
0x180010e5d  add     rsp, 20h
0x180010e61  pop     rbx
0x180010e62  retn
```
