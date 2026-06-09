# BfReturnedWalkContextAvlDeleteFunction

- ea: `0x140020c54`
- end: `0x140020c67`
- name: `BfReturnedWalkContextAvlDeleteFunction`
- size: `19`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140020ae0`
- `0x140024e50`

## callees

- `0x140020d60`

## pseudocode

```c
void __fastcall BfReturnedWalkContextAvlDeleteFunction(__int64 a1)
{
  BfDereferenceMappingListEntry((volatile signed __int64 *)(a1 - 16));
}

```

## disassembly

```asm
0x140020c54  sub     rsp, 28h
0x140020c58  add     rcx, 0FFFFFFFFFFFFFFF0h; Entry
0x140020c5c  call    BfDereferenceMappingListEntry
0x140020c61  add     rsp, 28h
0x140020c65  retn
```
