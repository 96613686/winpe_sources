# DetourTransactionCommit()

- ea: `0x40ddf0`
- end: `0x40ddf8`
- name: `_DetourTransactionCommit@0`
- size: `8`
- prototype: `int __stdcall()`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x409e9d`
- `0x409f13`

## callees

- `0x40de00`

## pseudocode

```c
int __stdcall DetourTransactionCommit()
{
  return DetourTransactionCommitEx(0);
}

```

## disassembly

```asm
0x40ddf0  push    0
0x40ddf2  call    _DetourTransactionCommitEx@4; DetourTransactionCommitEx(x)
0x40ddf7  retn
```
