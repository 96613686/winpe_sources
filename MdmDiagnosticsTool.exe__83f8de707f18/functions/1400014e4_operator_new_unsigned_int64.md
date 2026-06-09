# operator new(unsigned __int64)

- ea: `0x1400014e4`
- end: `0x140001515`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140002dd0`
- `0x140003184`
- `0x14000727c`
- `0x14000a2cc`

## callees

- `0x1400014e4`
- `0x140001688`
- `0x140001db6`

## import_xrefs

- `msvcrt!malloc` at `0x1400014fe`
- `msvcrt!malloc` at `0x1400014fe`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
      std::_Xbad_alloc();
  }
  return result;
}

```

## disassembly

```asm
0x1400014e4  push    rbx
0x1400014e6  sub     rsp, 20h
0x1400014ea  mov     rbx, rcx
0x1400014ed  jmp     short loc_1400014FE
0x1400014ef  mov     rcx, rbx; Size
0x1400014f2  call    _callnewh_0
0x1400014f7  test    eax, eax
0x1400014f9  jz      short loc_14000150F
0x1400014fb  mov     rcx, rbx; Size
0x1400014fe  call    cs:__imp_malloc
0x140001504  test    rax, rax
0x140001507  jz      short loc_1400014EF
0x140001509  add     rsp, 20h
0x14000150d  pop     rbx
0x14000150e  retn
0x14000150f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
