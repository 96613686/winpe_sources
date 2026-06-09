# j_common_control87

- ea: `0x14001ae10`
- end: `0x14001ae15`
- name: `j_common_control87`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140019ee4`

## callees

- `0x14001ae18`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall j_common_control87(int a1, int a2)
{
  return common_control87(a1, a2);
}

```

## disassembly

```asm
0x14001ae10  jmp     common_control87
```
