# operator new(unsigned __int64)

- ea: `0x180001b48`
- end: `0x180001b79`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d28`
- `0x180006d14`
- `0x1800073c7`

## callees

- `0x180001b48`
- `0x180001e88`
- `0x1800024f6`

## import_xrefs

- `msvcrt!malloc` at `0x180001b62`
- `msvcrt!malloc` at `0x180001b62`

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
0x180001b48  push    rbx
0x180001b4a  sub     rsp, 20h
0x180001b4e  mov     rbx, rcx
0x180001b51  jmp     short loc_180001B62
0x180001b53  mov     rcx, rbx; Size
0x180001b56  call    _callnewh_0
0x180001b5b  test    eax, eax
0x180001b5d  jz      short loc_180001B73
0x180001b5f  mov     rcx, rbx; Size
0x180001b62  call    cs:__imp_malloc
0x180001b68  test    rax, rax
0x180001b6b  jz      short loc_180001B53
0x180001b6d  add     rsp, 20h
0x180001b71  pop     rbx
0x180001b72  retn
0x180001b73  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
