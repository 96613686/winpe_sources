# operator new[](unsigned __int64)

- ea: `0x180001150`
- end: `0x180001155`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023b0`
- `0x1800035d0`
- `0x180003e54`
- `0x180003f08`
- `0x18000428c`

## callees

- `0x180001104`

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
0x180001150  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
