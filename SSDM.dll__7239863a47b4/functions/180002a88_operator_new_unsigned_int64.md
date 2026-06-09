# operator new(unsigned __int64)

- ea: `0x180002a88`
- end: `0x180002ab9`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180002d78`
- `0x180005b40`
- `0x180005ec0`
- `0x1800062cc`
- `0x1800069f0`
- `0x180006fe4`
- `0x18000720c`
- `0x180007290`
- `0x180007334`
- `0x180009b70`
- `0x18000bc38`
- `0x18000c334`
- `0x18000c610`
- `0x18000c670`
- `0x18000c8c4`
- `0x18000c9a8`
- `0x18000d654`
- `0x18000f1f7`
- `0x18000f73c`

## callees

- `0x180002a88`
- `0x180002bc8`
- `0x180002ea4`

## import_xrefs

- `msvcrt!malloc` at `0x180002aa2`
- `msvcrt!malloc` at `0x180002aa2`

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
0x180002a88  push    rbx
0x180002a8a  sub     rsp, 20h
0x180002a8e  mov     rbx, rcx
0x180002a91  jmp     short loc_180002AA2
0x180002a93  mov     rcx, rbx; Size
0x180002a96  call    _callnewh_0
0x180002a9b  test    eax, eax
0x180002a9d  jz      short loc_180002AB3
0x180002a9f  mov     rcx, rbx; Size
0x180002aa2  call    cs:__imp_malloc
0x180002aa8  test    rax, rax
0x180002aab  jz      short loc_180002A93
0x180002aad  add     rsp, 20h
0x180002ab1  pop     rbx
0x180002ab2  retn
0x180002ab3  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
