# operator new[](unsigned __int64)

- ea: `0x18000149c`
- end: `0x1800014a1`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800035f4`
- `0x180004f8c`
- `0x1800060e0`
- `0x180009fb4`
- `0x180012df4`
- `0x18001e98c`
- `0x18001eb2c`
- `0x18001ef70`
- `0x18001f07c`
- `0x18001fd04`

## callees

- `0x18000145c`

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
0x18000149c  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
