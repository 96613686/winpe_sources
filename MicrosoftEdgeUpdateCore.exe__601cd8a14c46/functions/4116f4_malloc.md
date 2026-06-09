# _malloc

- ea: `0x4116f4`
- end: `0x4116ff`
- name: `_malloc`
- size: `11`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x402488`
- `0x4038ac`
- `0x403e80`
- `0x404008`
- `0x4040fb`
- `0x40439d`
- `0x4053c7`
- `0x4100b4`
- `0x41ddac`

## callees

- `0x41627f`

## pseudocode

```c
void *__cdecl malloc(size_t Size)
{
  return _malloc_base(Size);
}

```

## disassembly

```asm
0x4116f4  mov     edi, edi
0x4116f6  push    ebp
0x4116f7  mov     ebp, esp
0x4116f9  pop     ebp
0x4116fa  jmp     __malloc_base
```
