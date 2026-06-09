# wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)

- ea: `0x180008670`
- end: `0x1800086b6`
- name: `??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `70`
- prototype: `void **__fastcall(void **, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dd00`

## callees

- `0x180008670`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086ae`

## pseudocode

```c
void **__fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(void **a1, void **a2)
{
  void *v2; // rax
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  return a1;
}

```

## disassembly

```asm
0x180008670  mov     [rsp+arg_0], rbx
0x180008675  push    rdi
0x180008676  sub     rsp, 20h
0x18000867a  mov     rax, [rdx]
0x18000867d  mov     rbx, rcx
0x180008680  mov     qword ptr [rdx], 0
0x180008687  mov     rdi, [rcx]
0x18000868a  mov     [rcx], rax
0x18000868d  test    rdi, rdi
0x180008690  jnz     short loc_1800086A0
0x180008692  mov     rax, rbx
0x180008695  mov     rbx, [rsp+28h+arg_0]
0x18000869a  add     rsp, 20h
0x18000869e  pop     rdi
0x18000869f  retn
0x1800086a0  call    cs:__imp_GetProcessHeap
0x1800086a6  mov     r8, rdi; lpMem
0x1800086a9  xor     edx, edx; dwFlags
0x1800086ab  mov     rcx, rax; hHeap
0x1800086ae  call    cs:__imp_HeapFree
0x1800086b4  jmp     short loc_180008692
```
