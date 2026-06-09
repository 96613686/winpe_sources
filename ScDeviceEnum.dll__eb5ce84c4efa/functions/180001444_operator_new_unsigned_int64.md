# operator new(unsigned __int64)

- ea: `0x180001444`
- end: `0x180001475`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x180002228`
- `0x180002cf8`
- `0x180009164`
- `0x18000a9f8`
- `0x18000b4a0`
- `0x18000bb00`
- `0x18000be04`
- `0x18000be44`
- `0x18000cf60`
- `0x18000d9cc`
- `0x18000db7c`
- `0x18000e228`
- `0x18000eabc`
- `0x18000fd90`
- `0x180010dd0`
- `0x18001cfb4`
- `0x18001d5c8`
- `0x18001ea72`

## callees

- `0x180001444`
- `0x1800015e8`
- `0x180001ed6`

## import_xrefs

- `msvcrt!malloc` at `0x18000145e`
- `msvcrt!malloc` at `0x18000145e`

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
0x180001444  push    rbx
0x180001446  sub     rsp, 20h
0x18000144a  mov     rbx, rcx
0x18000144d  jmp     short loc_18000145E
0x18000144f  mov     rcx, rbx; Size
0x180001452  call    _callnewh_0
0x180001457  test    eax, eax
0x180001459  jz      short loc_18000146F
0x18000145b  mov     rcx, rbx; Size
0x18000145e  call    cs:__imp_malloc
0x180001464  test    rax, rax
0x180001467  jz      short loc_18000144F
0x180001469  add     rsp, 20h
0x18000146d  pop     rbx
0x18000146e  retn
0x18000146f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
