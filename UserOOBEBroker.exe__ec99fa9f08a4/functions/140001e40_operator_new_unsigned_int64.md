# operator new(unsigned __int64)

- ea: `0x140001e40`
- end: `0x140001e71`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400025d8`
- `0x14000613c`
- `0x14000e6c7`

## callees

- `0x140001e40`
- `0x140001fe8`
- `0x14000260b`

## import_xrefs

- `msvcrt!malloc` at `0x140001e5a`
- `msvcrt!malloc` at `0x140001e5a`

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
0x140001e40  push    rbx
0x140001e42  sub     rsp, 20h
0x140001e46  mov     rbx, rcx
0x140001e49  jmp     short loc_140001E5A
0x140001e4b  mov     rcx, rbx; Size
0x140001e4e  call    _callnewh_0
0x140001e53  test    eax, eax
0x140001e55  jz      short loc_140001E6B
0x140001e57  mov     rcx, rbx; Size
0x140001e5a  call    cs:__imp_malloc
0x140001e60  test    rax, rax
0x140001e63  jz      short loc_140001E4B
0x140001e65  add     rsp, 20h
0x140001e69  pop     rbx
0x140001e6a  retn
0x140001e6b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
