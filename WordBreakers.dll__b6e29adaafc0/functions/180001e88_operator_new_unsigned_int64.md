# operator new(unsigned __int64)

- ea: `0x180001e88`
- end: `0x180001eb9`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180002c20`
- `0x180002f00`
- `0x18000656c`
- `0x1800065a4`
- `0x180006754`
- `0x1800069ac`
- `0x18000bb6a`

## callees

- `0x180001e88`
- `0x180002038`
- `0x180002656`

## import_xrefs

- `msvcrt!malloc` at `0x180001ea2`
- `msvcrt!malloc` at `0x180001ea2`

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
0x180001e88  push    rbx
0x180001e8a  sub     rsp, 20h
0x180001e8e  mov     rbx, rcx
0x180001e91  jmp     short loc_180001EA2
0x180001e93  mov     rcx, rbx; Size
0x180001e96  call    _callnewh_0
0x180001e9b  test    eax, eax
0x180001e9d  jz      short loc_180001EB3
0x180001e9f  mov     rcx, rbx; Size
0x180001ea2  call    cs:__imp_malloc
0x180001ea8  test    rax, rax
0x180001eab  jz      short loc_180001E93
0x180001ead  add     rsp, 20h
0x180001eb1  pop     rbx
0x180001eb2  retn
0x180001eb3  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
