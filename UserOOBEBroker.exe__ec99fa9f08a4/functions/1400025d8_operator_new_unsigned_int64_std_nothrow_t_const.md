# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1400025d8`
- end: `0x1400025f7`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `31`
- prototype: `void *__fastcall(unsigned __int64, const struct std::nothrow_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140002600`
- `0x140006f10`
- `0x140006ff0`
- `0x1400070d0`
- `0x1400071ac`
- `0x140007264`
- `0x140008d40`

## callees

- `0x140001e40`
- `0x1400025d8`

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
0x1400025d8  sub     rsp, 38h
0x1400025dc  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1400025e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400025ea  nop
0x1400025eb  jmp     short loc_1400025F2
0x1400025ed  mov     rax, [rsp+38h+arg_10]
0x1400025f2  add     rsp, 38h
0x1400025f6  retn
```
