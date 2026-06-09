# BfCachedWalkContextAvlDeleteFunction

- ea: `0x140020eec`
- end: `0x140020eff`
- name: `BfCachedWalkContextAvlDeleteFunction`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140020e04`

## callees

- `0x140020d60`

## pseudocode

```c
void __fastcall BfCachedWalkContextAvlDeleteFunction(__int64 a1)
{
  BfDereferenceMappingListEntry((volatile signed __int64 *)(a1 - 40));
}

```

## disassembly

```asm
0x140020eec  sub     rsp, 28h
0x140020ef0  add     rcx, 0FFFFFFFFFFFFFFD8h; Entry
0x140020ef4  call    BfDereferenceMappingListEntry
0x140020ef9  add     rsp, 28h
0x140020efd  retn
```
