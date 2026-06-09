# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x140003430`
- end: `0x14000345b`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `43`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400034a4`
- `0x14000354c`
- `0x1400036f0`
- `0x14000471c`

## callees

- `0x140003430`
- `0x14000345c`
- `0x1400040b4`

## pseudocode

```c
void *__fastcall std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64 a1)
{
  if ( !a1 )
    return 0;
  if ( a1 < 0x1000 )
    return std::_Default_allocate_traits::_Allocate(a1);
  return (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>();
}

```

## disassembly

```asm
0x140003430  sub     rsp, 28h
0x140003434  test    rcx, rcx
0x140003437  jnz     short loc_14000343D
0x140003439  xor     eax, eax
0x14000343b  jmp     short loc_140003456
0x14000343d  cmp     rcx, 1000h
0x140003444  jb      short loc_14000344D
0x140003446  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x14000344b  jmp     short loc_140003456
0x14000344d  add     rsp, 28h
0x140003451  jmp     ?_Allocate@_Default_allocate_traits@std@@SAPEAX_K@Z; std::_Default_allocate_traits::_Allocate(unsigned __int64)
0x140003456  add     rsp, 28h
0x14000345a  retn
```
