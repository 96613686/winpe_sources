# operator new(unsigned __int64,std::nothrow_t const &)

- ea: `0x1800021ac`
- end: `0x1800021c8`
- name: `??2@YAPEAX_KAEBUnothrow_t@std@@@Z`
- size: `28`
- prototype: `void *__fastcall(size_t, const struct std::nothrow_t *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ea0`
- `0x180003050`
- `0x18000c42c`
- `0x18000c5a0`
- `0x18000cc9c`
- `0x18000d190`
- `0x18000dd6c`
- `0x18000df30`
- `0x180010040`
- `0x1800102c0`
- `0x180010768`

## callees

- `0x1800021ac`
- `0x1800021fc`

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
0x1800021ac  sub     rsp, 38h
0x1800021b0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800021b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800021be  jmp     short loc_1800021C2
0x1800021c0  xor     eax, eax
0x1800021c2  add     rsp, 38h
0x1800021c6  retn
```
