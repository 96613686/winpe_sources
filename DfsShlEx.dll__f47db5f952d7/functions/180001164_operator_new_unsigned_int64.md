# operator new(unsigned __int64)

- ea: `0x180001164`
- end: `0x180001195`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x18000119c`
- `0x180001348`
- `0x180002468`
- `0x180004444`
- `0x180004550`
- `0x18000463c`
- `0x180004724`
- `0x180004800`
- `0x18000aae3`

## callees

- `0x180001164`
- `0x1800014a8`
- `0x18000249b`

## import_xrefs

- `msvcrt!malloc` at `0x18000117e`
- `msvcrt!malloc` at `0x18000117e`

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
0x180001164  push    rbx
0x180001166  sub     rsp, 20h
0x18000116a  mov     rbx, rcx
0x18000116d  jmp     short loc_18000117E
0x18000116f  mov     rcx, rbx; Size
0x180001172  call    _callnewh_0
0x180001177  test    eax, eax
0x180001179  jz      short loc_18000118F
0x18000117b  mov     rcx, rbx; Size
0x18000117e  call    cs:__imp_malloc
0x180001184  test    rax, rax
0x180001187  jz      short loc_18000116F
0x180001189  add     rsp, 20h
0x18000118d  pop     rbx
0x18000118e  retn
0x18000118f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
