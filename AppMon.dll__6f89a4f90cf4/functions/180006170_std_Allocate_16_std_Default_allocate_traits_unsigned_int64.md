# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x180006170`
- end: `0x18000618a`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `26`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800061d0`
- `0x180007dc0`
- `0x180008010`
- `0x1800080c0`
- `0x180009960`
- `0x18000a7f8`
- `0x18000ab8c`
- `0x18000d628`

## callees

- `0x1800026fc`
- `0x180006170`
- `0x180006190`

## pseudocode

```c
void *__fastcall std::_Allocate<16,std::_Default_allocate_traits>(size_t a1)
{
  if ( !a1 )
    return 0;
  if ( a1 >= 0x1000 )
    return (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>();
  return operator new(a1);
}

```

## disassembly

```asm
0x180006170  test    rcx, rcx
0x180006173  jnz     short loc_180006178
0x180006175  xor     eax, eax
0x180006177  retn
0x180006178  cmp     rcx, 1000h
0x18000617f  jnb     ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x180006185  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
