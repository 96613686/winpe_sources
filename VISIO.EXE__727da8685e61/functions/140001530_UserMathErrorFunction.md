# UserMathErrorFunction

- ea: `0x140001530`
- end: `0x140001533`
- name: `UserMathErrorFunction`
- size: `3`
- prototype: `int __cdecl(struct _exception *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001520`
- `0x140001540`
- `0x140001750`

## pseudocode

```c
__int64 __fastcall UserMathErrorFunction(struct _exception *a1)
{
  return 0;
}

```

## disassembly

```asm
0x140001530  xor     eax, eax
0x140001532  retn
```
