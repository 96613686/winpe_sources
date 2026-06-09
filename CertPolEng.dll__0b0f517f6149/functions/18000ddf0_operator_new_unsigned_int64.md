# operator new(unsigned __int64)

- ea: `0x18000ddf0`
- end: `0x18000de21`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d90`
- `0x1800043d0`
- `0x1800077b0`
- `0x18000caa0`
- `0x18000edc0`
- `0x18000f2ec`
- `0x1800148fc`
- `0x180014c2c`

## callees

- `0x18000ddf0`
- `0x18000df98`
- `0x18000e886`

## import_xrefs

- `msvcrt!malloc` at `0x18000de0a`
- `msvcrt!malloc` at `0x18000de0a`

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
0x18000ddf0  push    rbx
0x18000ddf2  sub     rsp, 20h
0x18000ddf6  mov     rbx, rcx
0x18000ddf9  jmp     short loc_18000DE0A
0x18000ddfb  mov     rcx, rbx; Size
0x18000ddfe  call    _callnewh_0
0x18000de03  test    eax, eax
0x18000de05  jz      short loc_18000DE1B
0x18000de07  mov     rcx, rbx; Size
0x18000de0a  call    cs:__imp_malloc
0x18000de10  test    rax, rax
0x18000de13  jz      short loc_18000DDFB
0x18000de15  add     rsp, 20h
0x18000de19  pop     rbx
0x18000de1a  retn
0x18000de1b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
