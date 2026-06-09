# operator new(unsigned __int64)

- ea: `0x1800020c4`
- end: `0x1800020f5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `55`
- callee_count: `3`
- tags: ``

## callers

- `0x18000254c`
- `0x18000276c`
- `0x1800027ac`
- `0x18000392c`
- `0x1800039e0`
- `0x180003ab8`
- `0x180003b6c`
- `0x180003c20`
- `0x1800060cc`
- `0x1800087f4`
- `0x18000bbe0`
- `0x18000c640`
- `0x18000c720`
- `0x18000c83c`
- `0x18000c958`
- `0x18000ca50`
- `0x18000cb04`
- `0x18000cbb8`
- `0x18000cc6c`
- `0x18000cd20`
- `0x18000cdd4`
- `0x18000ce88`
- `0x18000cf74`
- `0x18000d060`
- `0x18000d14c`
- `0x18000d238`
- `0x18000d2ec`
- `0x18000d3a0`
- `0x18000d454`
- `0x18000d508`
- `0x18000d5e4`
- `0x18000d6c0`
- `0x18000d798`
- `0x18000d870`
- `0x180012c38`
- `0x180013898`
- `0x18001d820`
- `0x18001d93c`
- `0x18001d9f0`
- `0x18001daa4`
- `0x18001db58`
- `0x18001dc44`
- `0x18001dd30`
- `0x18001de08`
- `0x18001f4a0`
- `0x1800294a0`
- `0x18002fdc4`
- `0x1800309e0`
- `0x18003158c`
- `0x180033d00`

## callees

- `0x1800020c4`
- `0x1800022c8`
- `0x18002676c`

## import_xrefs

- `msvcrt!malloc` at `0x1800020de`
- `msvcrt!malloc` at `0x1800020de`

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
0x1800020c4  push    rbx
0x1800020c6  sub     rsp, 20h
0x1800020ca  mov     rbx, rcx
0x1800020cd  jmp     short loc_1800020DE
0x1800020cf  mov     rcx, rbx; Size
0x1800020d2  call    _callnewh_0
0x1800020d7  test    eax, eax
0x1800020d9  jz      short loc_1800020EF
0x1800020db  mov     rcx, rbx; Size
0x1800020de  call    cs:__imp_malloc
0x1800020e4  test    rax, rax
0x1800020e7  jz      short loc_1800020CF
0x1800020e9  add     rsp, 20h
0x1800020ed  pop     rbx
0x1800020ee  retn
0x1800020ef  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
