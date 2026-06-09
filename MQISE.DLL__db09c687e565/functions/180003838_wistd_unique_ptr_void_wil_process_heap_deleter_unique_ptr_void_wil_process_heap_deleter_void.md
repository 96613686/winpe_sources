# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180003838`
- end: `0x180003868`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fa54`

## callees

- `0x180003838`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000384d`
- `KERNEL32!GetProcessHeap` at `0x18000384d`
- `KERNEL32!HeapFree` at `0x18000385b`
- `KERNEL32!HeapFree` at `0x18000385b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180003838  push    rbx
0x18000383a  sub     rsp, 20h
0x18000383e  mov     rbx, [rcx]
0x180003841  mov     qword ptr [rcx], 0
0x180003848  test    rbx, rbx
0x18000384b  jz      short loc_180003862
0x18000384d  call    cs:__imp_GetProcessHeap
0x180003853  mov     rcx, rax; hHeap
0x180003856  mov     r8, rbx; lpMem
0x180003859  xor     edx, edx; dwFlags
0x18000385b  call    cs:__imp_HeapFree
0x180003861  nop
0x180003862  add     rsp, 20h
0x180003866  pop     rbx
0x180003867  retn
```
