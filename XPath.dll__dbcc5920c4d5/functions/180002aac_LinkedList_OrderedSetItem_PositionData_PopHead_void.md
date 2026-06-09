# LinkedList<OrderedSetItem<PositionData>>::PopHead(void)

- ea: `0x180002aac`
- end: `0x180002acf`
- name: `?PopHead@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@QEAAPEAV?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@XZ`
- size: `35`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002464`
- `0x180002784`
- `0x1800029ac`
- `0x180002c10`

## callees

- `0x180002aac`

## pseudocode

```c
_QWORD *__fastcall LinkedList<OrderedSetItem<PositionData>>::PopHead(__int64 a1)
{
  _QWORD *result; // rax

  result = *(_QWORD **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = *result;
  *result = 0;
  if ( result == *(_QWORD **)(a1 + 16) )
    *(_QWORD *)(a1 + 16) = 0;
  --*(_DWORD *)a1;
  return result;
}

```

## disassembly

```asm
0x180002aac  mov     rax, [rcx+8]
0x180002ab0  mov     rdx, [rax]
0x180002ab3  mov     [rcx+8], rdx
0x180002ab7  mov     qword ptr [rax], 0
0x180002abe  cmp     rax, [rcx+10h]
0x180002ac2  jnz     short loc_180002ACC
0x180002ac4  mov     qword ptr [rcx+10h], 0
0x180002acc  dec     dword ptr [rcx]
0x180002ace  retn
```
