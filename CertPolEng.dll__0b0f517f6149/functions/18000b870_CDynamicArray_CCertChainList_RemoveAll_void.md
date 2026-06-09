# CDynamicArray<CCertChainList *>::RemoveAll(void)

- ea: `0x18000b870`
- end: `0x18000b8b3`
- name: `?RemoveAll@?$CDynamicArray@PEAVCCertChainList@@@@QEAAXXZ`
- size: `67`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b810`
- `0x180013c28`
- `0x180013c90`

## callees

- `0x18000b870`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b885`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b885`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b893`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b893`

## pseudocode

```c
void __fastcall CDynamicArray<CCertChainList *>::RemoveAll(__int64 a1)
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
0x18000b870  mov     [rsp+arg_0], rbx
0x18000b875  push    rdi
0x18000b876  sub     rsp, 20h
0x18000b87a  mov     rdi, [rcx]
0x18000b87d  mov     rbx, rcx
0x18000b880  test    rdi, rdi
0x18000b883  jz      short loc_18000B8A8
0x18000b885  call    cs:__imp_GetProcessHeap
0x18000b88b  mov     r8, rdi; lpMem
0x18000b88e  xor     edx, edx; dwFlags
0x18000b890  mov     rcx, rax; hHeap
0x18000b893  call    cs:__imp_HeapFree
0x18000b899  mov     qword ptr [rbx], 0
0x18000b8a0  mov     qword ptr [rbx+8], 0
0x18000b8a8  mov     rbx, [rsp+28h+arg_0]
0x18000b8ad  add     rsp, 20h
0x18000b8b1  pop     rdi
0x18000b8b2  retn
```
