# operator new[](unsigned __int64)

- ea: `0x18000146c`
- end: `0x180001471`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180003534`
- `0x180004ecc`
- `0x180006020`
- `0x180009ef4`
- `0x180012d34`
- `0x18001e8cc`
- `0x18001ea6c`
- `0x18001eeb0`
- `0x18001efbc`
- `0x18001fc44`

## callees

- `0x18000142c`

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
0x18000146c  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
