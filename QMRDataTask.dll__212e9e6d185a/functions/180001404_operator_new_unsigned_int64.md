# operator new(unsigned __int64)

- ea: `0x180001404`
- end: `0x180001435`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180002138`
- `0x180002150`
- `0x180002454`
- `0x18000254c`
- `0x1800041a4`
- `0x180007348`
- `0x18001475a`
- `0x1800147d2`

## callees

- `0x180001404`
- `0x1800015a8`
- `0x180001c96`

## import_xrefs

- `msvcrt!malloc` at `0x18000141e`
- `msvcrt!malloc` at `0x18000141e`

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
0x180001404  push    rbx
0x180001406  sub     rsp, 20h
0x18000140a  mov     rbx, rcx
0x18000140d  jmp     short loc_18000141E
0x18000140f  mov     rcx, rbx; Size
0x180001412  call    _callnewh_0
0x180001417  test    eax, eax
0x180001419  jz      short loc_18000142F
0x18000141b  mov     rcx, rbx; Size
0x18000141e  call    cs:__imp_malloc
0x180001424  test    rax, rax
0x180001427  jz      short loc_18000140F
0x180001429  add     rsp, 20h
0x18000142d  pop     rbx
0x18000142e  retn
0x18000142f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
