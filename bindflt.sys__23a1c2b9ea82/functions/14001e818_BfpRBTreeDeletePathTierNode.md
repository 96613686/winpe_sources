# BfpRBTreeDeletePathTierNode

- ea: `0x14001e818`
- end: `0x14001e84d`
- name: `BfpRBTreeDeletePathTierNode`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e8c0`

## callees

- `0x14001e818`
- `0x14001e854`
- `0x14001e8c0`

## pseudocode

```c
void __fastcall BfpRBTreeDeletePathTierNode(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rbx
  unsigned __int64 v3; // rcx

  v2 = (_QWORD *)(a1 - 8);
  if ( (*(_DWORD *)(a1 - 8) & 2) == 0 )
  {
    v3 = v2[10];
    if ( v3 )
    {
      BfpDeletePathTree(v3, a2);
      v2[10] = 0;
    }
  }
  BfpDeletePathTierNode(v2);
}

```

## disassembly

```asm
0x14001e818  push    rbx
0x14001e81a  sub     rsp, 20h
0x14001e81e  lea     rbx, [rcx-8]
0x14001e822  mov     eax, [rbx]
0x14001e824  test    al, 2
0x14001e826  jnz     short loc_14001E83E
0x14001e828  mov     rcx, [rbx+50h]; P
0x14001e82c  test    rcx, rcx
0x14001e82f  jz      short loc_14001E83E
0x14001e831  call    BfpDeletePathTree
0x14001e836  mov     qword ptr [rbx+50h], 0
0x14001e83e  mov     rcx, rbx; P
0x14001e841  call    BfpDeletePathTierNode
0x14001e846  add     rsp, 20h
0x14001e84a  pop     rbx
0x14001e84b  retn
```
