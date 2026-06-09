# operator new(unsigned __int64)

- ea: `0x1800011c8`
- end: `0x1800011f9`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180005b7c`
- `0x1800078c8`
- `0x1800079c8`
- `0x180007ae4`
- `0x180008578`
- `0x18000c88f`
- `0x18000c90c`

## callees

- `0x1800011c8`
- `0x180001308`
- `0x180001b9c`

## import_xrefs

- `msvcrt!malloc` at `0x1800011e2`
- `msvcrt!malloc` at `0x1800011e2`

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
0x1800011c8  push    rbx
0x1800011ca  sub     rsp, 20h
0x1800011ce  mov     rbx, rcx
0x1800011d1  jmp     short loc_1800011E2
0x1800011d3  mov     rcx, rbx; Size
0x1800011d6  call    _callnewh_0
0x1800011db  test    eax, eax
0x1800011dd  jz      short loc_1800011F3
0x1800011df  mov     rcx, rbx; Size
0x1800011e2  call    cs:__imp_malloc
0x1800011e8  test    rax, rax
0x1800011eb  jz      short loc_1800011D3
0x1800011ed  add     rsp, 20h
0x1800011f1  pop     rbx
0x1800011f2  retn
0x1800011f3  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
