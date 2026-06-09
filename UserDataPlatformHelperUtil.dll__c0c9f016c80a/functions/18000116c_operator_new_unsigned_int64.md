# operator new[](unsigned __int64)

- ea: `0x18000116c`
- end: `0x180001171`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(size_t)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800028c0`
- `0x180005df8`
- `0x1800061e0`
- `0x180007aa0`
- `0x180008dc0`

## callees

- `0x180001184`

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
0x18000116c  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
