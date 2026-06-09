# operator new[](unsigned __int64)

- ea: `0x18000130c`
- end: `0x180001311`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180002760`
- `0x180002bf0`
- `0x180002ea0`
- `0x18000392c`
- `0x180005560`
- `0x1800065c8`
- `0x180007d7c`
- `0x180009e6c`
- `0x18000b06c`

## callees

- `0x1800012c0`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](size_t a1)
{
  return operator new(a1);
}

```

## disassembly

```asm
0x18000130c  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
