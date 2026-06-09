# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x14000a68c`
- end: `0x14000a69f`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `19`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140002b18`
- `0x140005ad8`
- `0x140005b78`
- `0x140007180`
- `0x14000720c`
- `0x140027f44`
- `0x140027ff4`
- `0x140028078`

## callees

- `0x14000a1c4`
- `0x14000a68c`

## pseudocode

```c
void *__fastcall operator new(size_t a1, const struct std::nothrow_t *a2)
{
  return operator new(a1);
}

```

## disassembly

```asm
0x14000a68c  sub     rsp, 28h
0x14000a690  call    ??2@YAPEAX_K@Z
0x14000a695  jmp     short loc_14000A699
0x14000a697  xor     eax, eax
0x14000a699  add     rsp, 28h
0x14000a69d  retn
```
