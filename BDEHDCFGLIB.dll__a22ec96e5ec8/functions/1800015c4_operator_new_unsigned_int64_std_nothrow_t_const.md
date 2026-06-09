# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800015c4`
- end: `0x1800015e3`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cb0`
- `0x180004dfc`
- `0x180006a48`
- `0x180007970`
- `0x180007af0`
- `0x18000a040`
- `0x18000a1c0`
- `0x18000a338`
- `0x18000a4f0`
- `0x18000a8e0`
- `0x18000ab70`
- `0x18000ad60`
- `0x18000ae70`
- `0x18000b094`
- `0x18000b2c0`
- `0x18000b590`
- `0x18000be90`
- `0x18000cc9c`
- `0x18000ed1c`

## callees

- `0x1800015c4`
- `0x180001c28`

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
0x1800015c4  sub     rsp, 38h
0x1800015c8  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800015d1  call    ??2@YAPEAX_K@Z
0x1800015d6  nop
0x1800015d7  jmp     short loc_1800015DE
0x1800015d9  mov     rax, [rsp+38h+arg_10]
0x1800015de  add     rsp, 38h
0x1800015e2  retn
```
