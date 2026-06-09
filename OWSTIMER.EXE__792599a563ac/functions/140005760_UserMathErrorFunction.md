# UserMathErrorFunction

- ea: `0x140005760`
- end: `0x140005763`
- name: `UserMathErrorFunction`
- size: `3`
- prototype: `int __cdecl(struct _exception *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140007de0`
- `0x140007eb0`

## pseudocode

```c
__int64 __fastcall UserMathErrorFunction(struct _exception *a1)
{
  return 0;
}

```

## disassembly

```asm
0x140005760  xor     eax, eax
0x140005762  retn
```
