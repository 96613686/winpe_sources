# DeletePSEPNodeList

- ea: `0x1800028c4`
- end: `0x1800028f1`
- name: `DeletePSEPNodeList`
- size: `45`
- prototype: `BOOL __fastcall(_QWORD *lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800018a0`
- `0x180002714`

## callees

- `0x1800028c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800028e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800028e0`

## pseudocode

```c
BOOL __fastcall DeletePSEPNodeList(_QWORD *lpMem)
{
  _QWORD *v1; // rbx
  void *v2; // r8
  BOOL result; // eax

  if ( lpMem )
  {
    v1 = lpMem;
    do
    {
      v2 = v1;
      v1 = (_QWORD *)*v1;
      result = HeapFree(hEpMapperHeap, 0, v2);
    }
    while ( v1 );
  }
  return result;
}

```

## disassembly

```asm
0x1800028c4  test    rcx, rcx
0x1800028c7  jz      short locret_1800028F0
0x1800028c9  push    rbx
0x1800028ca  sub     rsp, 20h
0x1800028ce  mov     rbx, rcx
0x1800028d1  mov     rcx, cs:hEpMapperHeap; hHeap
0x1800028d8  mov     r8, rbx; lpMem
0x1800028db  mov     rbx, [rbx]
0x1800028de  xor     edx, edx; dwFlags
0x1800028e0  call    cs:__imp_HeapFree
0x1800028e6  test    rbx, rbx
0x1800028e9  jnz     short loc_1800028D1
0x1800028eb  add     rsp, 20h
0x1800028ef  pop     rbx
0x1800028f0  retn
```
