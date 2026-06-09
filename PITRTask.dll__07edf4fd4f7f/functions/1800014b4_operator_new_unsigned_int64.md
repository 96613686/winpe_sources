# operator new(unsigned __int64)

- ea: `0x1800014b4`
- end: `0x1800014e5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d68`
- `0x1800048e0`
- `0x18000b634`
- `0x18000b72c`
- `0x18000b89c`
- `0x18000c660`
- `0x18000ea00`
- `0x18000ea40`
- `0x18000eb08`
- `0x180010d09`
- `0x180010d81`

## callees

- `0x1800014b4`
- `0x180001658`
- `0x180001d8d`

## import_xrefs

- `msvcrt!malloc` at `0x1800014ce`
- `msvcrt!malloc` at `0x1800014ce`

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
0x1800014b4  push    rbx
0x1800014b6  sub     rsp, 20h
0x1800014ba  mov     rbx, rcx
0x1800014bd  jmp     short loc_1800014CE
0x1800014bf  mov     rcx, rbx; Size
0x1800014c2  call    _callnewh_0
0x1800014c7  test    eax, eax
0x1800014c9  jz      short loc_1800014DF
0x1800014cb  mov     rcx, rbx; Size
0x1800014ce  call    cs:__imp_malloc
0x1800014d4  test    rax, rax
0x1800014d7  jz      short loc_1800014BF
0x1800014d9  add     rsp, 20h
0x1800014dd  pop     rbx
0x1800014de  retn
0x1800014df  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
