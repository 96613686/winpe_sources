# LinkedList<OrderedSetItem<PositionData>>::PushHeadOrInsertAfter(LinkedListItem<OrderedSetItem<PositionData>> *,LinkedListItem<OrderedSetItem<PositionData>> *)

- ea: `0x180002ad8`
- end: `0x180002b05`
- name: `?PushHeadOrInsertAfter@?$LinkedList@V?$OrderedSetItem@VPositionData@@@@@@AEAAXPEAV?$LinkedListItem@V?$OrderedSetItem@VPositionData@@@@@@0@Z`
- size: `45`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002464`
- `0x180002784`
- `0x1800029ac`
- `0x180002e9c`

## callees

- `0x180002ad8`

## pseudocode

```c
__int64 __fastcall LinkedList<OrderedSetItem<PositionData>>::PushHeadOrInsertAfter(
        __int64 a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 result; // rax

  if ( a2 )
  {
    result = *a2;
    *a3 = *a2;
    *a2 = (__int64)a3;
  }
  else
  {
    result = *(_QWORD *)(a1 + 8);
    if ( result )
      *a3 = result;
    *(_QWORD *)(a1 + 8) = a3;
  }
  if ( a2 == *(__int64 **)(a1 + 16) )
    *(_QWORD *)(a1 + 16) = a3;
  ++*(_DWORD *)a1;
  return result;
}

```

## disassembly

```asm
0x180002ad8  test    rdx, rdx
0x180002adb  jnz     short loc_180002AEF
0x180002add  mov     rax, [rcx+8]
0x180002ae1  test    rax, rax
0x180002ae4  jz      short loc_180002AE9
0x180002ae6  mov     [r8], rax
0x180002ae9  mov     [rcx+8], r8
0x180002aed  jmp     short loc_180002AF8
0x180002aef  mov     rax, [rdx]
0x180002af2  mov     [r8], rax
0x180002af5  mov     [rdx], r8
0x180002af8  cmp     rdx, [rcx+10h]
0x180002afc  jnz     short loc_180002B02
0x180002afe  mov     [rcx+10h], r8
0x180002b02  inc     dword ptr [rcx]
0x180002b04  retn
```
