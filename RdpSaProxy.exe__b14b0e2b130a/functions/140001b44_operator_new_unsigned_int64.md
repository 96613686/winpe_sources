# operator new(unsigned __int64)

- ea: `0x140001b44`
- end: `0x140001b75`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140001540`
- `0x140001d18`
- `0x140005836`

## callees

- `0x140001b44`
- `0x140001e78`
- `0x1400024ac`

## import_xrefs

- `msvcrt!malloc` at `0x140001b5e`
- `msvcrt!malloc` at `0x140001b5e`

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
0x140001b44  push    rbx
0x140001b46  sub     rsp, 20h
0x140001b4a  mov     rbx, rcx
0x140001b4d  jmp     short loc_140001B5E
0x140001b4f  mov     rcx, rbx; Size
0x140001b52  call    _callnewh_0
0x140001b57  test    eax, eax
0x140001b59  jz      short loc_140001B6F
0x140001b5b  mov     rcx, rbx; Size
0x140001b5e  call    cs:__imp_malloc
0x140001b64  test    rax, rax
0x140001b67  jz      short loc_140001B4F
0x140001b69  add     rsp, 20h
0x140001b6d  pop     rbx
0x140001b6e  retn
0x140001b6f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
