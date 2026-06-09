# SP_MEM<ulong>::operator=(CTypeWrapper<ulong *>)

- ea: `0x18000c848`
- end: `0x18000c88f`
- name: `??4?$SP_MEM@K@@QEAAAEAV0@V?$CTypeWrapper@PEAK@@@Z`
- size: `71`
- prototype: `void **__fastcall(void **, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e30`

## callees

- `0x18000c848`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c873`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c873`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c865`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c865`

## pseudocode

```c
void **__fastcall SP_MEM<unsigned long>::operator=(void **a1, void *a2)
{
  void *v2; // rsi
  HANDLE ProcessHeap; // rax
  void **result; // rax

  v2 = *a1;
  if ( *a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  result = a1;
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x18000c848  mov     [rsp+arg_0], rbx
0x18000c84d  mov     [rsp+arg_8], rsi
0x18000c852  push    rdi
0x18000c853  sub     rsp, 20h
0x18000c857  mov     rsi, [rcx]
0x18000c85a  mov     rbx, rdx
0x18000c85d  mov     rdi, rcx
0x18000c860  test    rsi, rsi
0x18000c863  jz      short loc_18000C879
0x18000c865  call    cs:__imp_GetProcessHeap
0x18000c86b  mov     r8, rsi; lpMem
0x18000c86e  xor     edx, edx; dwFlags
0x18000c870  mov     rcx, rax; hHeap
0x18000c873  call    cs:__imp_HeapFree
0x18000c879  mov     rsi, [rsp+28h+arg_8]
0x18000c87e  mov     rax, rdi
0x18000c881  mov     [rdi], rbx
0x18000c884  mov     rbx, [rsp+28h+arg_0]
0x18000c889  add     rsp, 20h
0x18000c88d  pop     rdi
0x18000c88e  retn
```
