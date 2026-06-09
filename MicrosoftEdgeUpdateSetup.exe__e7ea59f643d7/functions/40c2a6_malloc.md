# _malloc

- ea: `0x40c2a6`
- end: `0x40c2b1`
- name: `_malloc`
- size: `11`
- prototype: `void *__cdecl(size_t Size)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x4056bc`
- `0x405bd0`
- `0x405d21`
- `0x405df6`
- `0x405ecb`
- `0x405ff0`
- `0x4061ae`
- `0x4061f3`
- `0x40afd4`
- `0x4196fe`

## callees

- `0x4109f3`

## pseudocode

```c
void *__cdecl malloc(size_t Size)
{
  return _malloc_base(Size);
}

```

## disassembly

```asm
0x40c2a6  mov     edi, edi
0x40c2a8  push    ebp
0x40c2a9  mov     ebp, esp
0x40c2ab  pop     ebp
0x40c2ac  jmp     __malloc_base
```
