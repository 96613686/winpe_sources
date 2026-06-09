# operator new[](unsigned __int64)

- ea: `0x180001230`
- end: `0x180001235`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ba8`
- `0x18000551c`
- `0x180005db4`
- `0x180005f64`
- `0x18000a58c`
- `0x18000f850`

## callees

- `0x18000123c`

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
0x180001230  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
