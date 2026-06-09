# CDynamicArray<IUnknown *>::RemoveAll(void)

- ea: `0x18000b840`
- end: `0x18000b87d`
- name: `?RemoveAll@?$CDynamicArray@PEAUIUnknown@@@@QEAAXXZ`
- size: `61`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b760`
- `0x180019a50`

## callees

- `0x18000b840`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b855`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b855`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b863`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b863`

## pseudocode

```c
void __fastcall CDynamicArray<IUnknown *>::RemoveAll(__int64 a1)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax

  v1 = *(void **)a1;
  if ( *(_QWORD *)a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000b840  mov     [rsp+arg_0], rbx
0x18000b845  push    rdi
0x18000b846  sub     rsp, 20h
0x18000b84a  mov     rdi, [rcx]
0x18000b84d  mov     rbx, rcx
0x18000b850  test    rdi, rdi
0x18000b853  jz      short loc_18000B872
0x18000b855  call    cs:__imp_GetProcessHeap
0x18000b85b  mov     r8, rdi; lpMem
0x18000b85e  xor     edx, edx; dwFlags
0x18000b860  mov     rcx, rax; hHeap
0x18000b863  call    cs:__imp_HeapFree
0x18000b869  xor     eax, eax
0x18000b86b  mov     [rbx], rax
0x18000b86e  mov     [rbx+8], rax
0x18000b872  mov     rbx, [rsp+28h+arg_0]
0x18000b877  add     rsp, 20h
0x18000b87b  pop     rdi
0x18000b87c  retn
```
