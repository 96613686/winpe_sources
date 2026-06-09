# operator new(unsigned __int64)

- ea: `0x1400014b4`
- end: `0x1400014e5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140002d4c`
- `0x1400030e8`
- `0x140006e80`
- `0x140009c97`

## callees

- `0x1400014b4`
- `0x140001658`
- `0x140001d86`

## import_xrefs

- `msvcrt!malloc` at `0x1400014ce`
- `msvcrt!malloc` at `0x1400014ce`

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
0x1400014b4  push    rbx
0x1400014b6  sub     rsp, 20h
0x1400014ba  mov     rbx, rcx
0x1400014bd  jmp     short loc_1400014CE
0x1400014bf  mov     rcx, rbx; Size
0x1400014c2  call    _callnewh_0
0x1400014c7  test    eax, eax
0x1400014c9  jz      short loc_1400014DF
0x1400014cb  mov     rcx, rbx; Size
0x1400014ce  call    cs:__imp_malloc
0x1400014d4  test    rax, rax
0x1400014d7  jz      short loc_1400014BF
0x1400014d9  add     rsp, 20h
0x1400014dd  pop     rbx
0x1400014de  retn
0x1400014df  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
