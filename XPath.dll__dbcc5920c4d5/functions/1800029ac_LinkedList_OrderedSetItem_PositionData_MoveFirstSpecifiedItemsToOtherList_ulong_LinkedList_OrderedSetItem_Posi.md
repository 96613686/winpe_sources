# LinkedList<OrderedSetItem<PositionData>>::MoveFirstSpecifiedItemsToOtherList(ulong,LinkedList<OrderedSetItem<PositionData>> *)

- ea: `0x1800029ac`
- end: `0x1800029ec`
- name: `?MoveFirstSpecifiedItemsToOtherList@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAXKPEAV1@@Z`
- size: `64`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800023d4`
- `0x18000284c`
- `0x180002e08`

## callees

- `0x1800029ac`
- `0x180002aac`
- `0x180002ad8`

## pseudocode

```c
void __fastcall LinkedList<OrderedSetItem<PositionData>>::MoveFirstSpecifiedItemsToOtherList(
        _DWORD *a1,
        int a2,
        __int64 a3)
{
  _DWORD *v4; // r9
  __int64 v5; // rax
  int v6; // r10d
  unsigned int v7; // r11d

  if ( a2 )
  {
    v4 = a1;
    do
    {
      if ( !*v4 )
        break;
      v5 = LinkedList<OrderedSetItem<PositionData>>::PopHead(v4);
      LinkedList<OrderedSetItem<PositionData>>::PushHeadOrInsertAfter(a3, *(_QWORD *)(a3 + 16), v5);
    }
    while ( v6 + 1 < v7 );
  }
}

```

## disassembly

```asm
0x1800029ac  test    edx, edx
0x1800029ae  jz      short locret_1800029EB
0x1800029b0  push    rbx
0x1800029b1  sub     rsp, 20h
0x1800029b5  mov     rbx, r8
0x1800029b8  mov     r11d, edx
0x1800029bb  mov     r9, rcx
0x1800029be  xor     r10d, r10d
0x1800029c1  cmp     dword ptr [r9], 0
0x1800029c5  jz      short loc_1800029E6
0x1800029c7  mov     rcx, r9
0x1800029ca  call    ?PopHead@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAPEAV?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@XZ; LinkedList<OrderedSetItem<PositionData>>::PopHead(void)
0x1800029cf  mov     rdx, [rbx+10h]
0x1800029d3  mov     r8, rax
0x1800029d6  mov     rcx, rbx
0x1800029d9  call    ?PushHeadOrInsertAfter@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@AEAAXPEAV?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@0@Z; LinkedList<OrderedSetItem<PositionData>>::PushHeadOrInsertAfter(LinkedListItem<OrderedSetItem<PositionData>> *,LinkedListItem<OrderedSetItem<PositionData>> *)
0x1800029de  inc     r10d
0x1800029e1  cmp     r10d, r11d
0x1800029e4  jb      short loc_1800029C1
0x1800029e6  add     rsp, 20h
0x1800029ea  pop     rbx
0x1800029eb  retn
```
