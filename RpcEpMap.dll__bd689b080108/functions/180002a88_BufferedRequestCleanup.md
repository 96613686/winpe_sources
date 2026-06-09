# BufferedRequestCleanup

- ea: `0x180002a88`
- end: `0x180002ad0`
- name: `BufferedRequestCleanup`
- size: `72`
- prototype: `BOOL __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023a8`
- `0x180003a1c`

## callees

- `0x180002a88`

## import_xrefs

- `RPCRT4!I_RpcFree` at `0x180002ab2`
- `RPCRT4!I_RpcFree` at `0x180002ab2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002aa3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002aa3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ac9`

## pseudocode

```c
BOOL __fastcall BufferedRequestCleanup(_QWORD *a1)
{
  void *v1; // r8
  void *v3; // rcx

  v1 = (void *)a1[6];
  if ( v1 )
    HeapFree(hEpMapperHeap, 0, v1);
  v3 = (void *)a1[8];
  if ( v3 )
    I_RpcFree(v3);
  return HeapFree(hEpMapperHeap, 0, a1);
}

```

## disassembly

```asm
0x180002a88  push    rbx
0x180002a8a  sub     rsp, 20h
0x180002a8e  mov     r8, [rcx+30h]; lpMem
0x180002a92  mov     rbx, rcx
0x180002a95  test    r8, r8
0x180002a98  jz      short loc_180002AA9
0x180002a9a  mov     rcx, cs:hEpMapperHeap; hHeap
0x180002aa1  xor     edx, edx; dwFlags
0x180002aa3  call    cs:__imp_HeapFree
0x180002aa9  mov     rcx, [rbx+40h]; Object
0x180002aad  test    rcx, rcx
0x180002ab0  jz      short loc_180002AB8
0x180002ab2  call    cs:__imp_I_RpcFree
0x180002ab8  mov     rcx, cs:hEpMapperHeap
0x180002abf  mov     r8, rbx
0x180002ac2  xor     edx, edx
0x180002ac4  add     rsp, 20h
0x180002ac8  pop     rbx
0x180002ac9  jmp     cs:__imp_HeapFree
```
