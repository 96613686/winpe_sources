# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x140001540`
- end: `0x14000155f`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400032f0`
- `0x140004750`

## callees

- `0x140001540`
- `0x140001b44`

## pseudocode

```c
void *__fastcall operator new(size_t a1, const struct std::nothrow_t *a2)
{
  void *result; // rax

  try
  {
    result = operator new(a1);
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001540  sub     rsp, 38h
0x140001544  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000154d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140001552  nop
0x140001553  jmp     short loc_14000155A
0x140001555  mov     rax, [rsp+38h+arg_10]
0x14000155a  add     rsp, 38h
0x14000155e  retn
```
