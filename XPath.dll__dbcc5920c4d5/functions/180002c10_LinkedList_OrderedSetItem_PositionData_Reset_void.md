# LinkedList<OrderedSetItem<PositionData>>::Reset(void)

- ea: `0x180002c10`
- end: `0x180002c42`
- name: `?Reset@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXXZ`
- size: `50`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000284c`
- `0x180002c48`
- `0x180002e08`
- `0x1800065ac`

## callees

- `0x180002438`
- `0x180002aac`
- `0x180002c10`

## pseudocode

```c
void __fastcall LinkedList<OrderedSetItem<PositionData>>::Reset(__int64 a1)
{
  void *v2; // rax

  while ( *(_QWORD *)(a1 + 8) )
  {
    v2 = (void *)LinkedList<OrderedSetItem<PositionData>>::PopHead(a1);
    if ( v2 )
      LinkedListItem<OrderedSetItem<PositionData>>::`scalar deleting destructor'(v2);
  }
}

```

## disassembly

```asm
0x180002c10  push    rbx
0x180002c12  sub     rsp, 20h
0x180002c16  cmp     qword ptr [rcx+8], 0
0x180002c1b  mov     rbx, rcx
0x180002c1e  jz      short loc_180002C3C
0x180002c20  mov     rcx, rbx
0x180002c23  call    ?PopHead@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAPEAV?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@XZ; LinkedList<OrderedSetItem<PositionData>>::PopHead(void)
0x180002c28  test    rax, rax
0x180002c2b  jz      short loc_180002C35
0x180002c2d  mov     rcx, rax; Block
0x180002c30  call    ??_G?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@QEAAPEAXI@Z; LinkedListItem<OrderedSetItem<PositionData>>::`scalar deleting destructor'(uint)
0x180002c35  cmp     qword ptr [rbx+8], 0
0x180002c3a  jnz     short loc_180002C20
0x180002c3c  add     rsp, 20h
0x180002c40  pop     rbx
0x180002c41  retn
```
