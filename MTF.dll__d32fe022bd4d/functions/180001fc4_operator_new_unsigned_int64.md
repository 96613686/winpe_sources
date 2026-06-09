# operator new(unsigned __int64)

- ea: `0x180001fc4`
- end: `0x180001ff5`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `53`
- callee_count: `3`
- tags: ``

## callers

- `0x180002d88`
- `0x180006e08`
- `0x180007da0`
- `0x180007df0`
- `0x180007eb0`
- `0x180007fa0`
- `0x1800080b0`
- `0x180008100`
- `0x180008190`
- `0x180008240`
- `0x18000cba4`
- `0x18000cbe4`
- `0x18000cc24`
- `0x18000cc78`
- `0x18000ccc4`
- `0x18000cfbc`
- `0x18000d208`
- `0x18000ffd0`
- `0x180010024`
- `0x18001134c`
- `0x18001398c`
- `0x1800140d4`
- `0x180014a00`
- `0x18001d120`
- `0x18001d190`
- `0x18001d1f4`
- `0x18001e088`
- `0x18001e260`
- `0x18001e2e0`
- `0x18001e914`
- `0x18001ed80`
- `0x18001fb10`
- `0x180020110`
- `0x180020e50`
- `0x180021db0`
- `0x180021e00`
- `0x180021e50`
- `0x180021ea0`
- `0x1800225bc`
- `0x180022ac4`
- `0x180025248`
- `0x18002533c`
- `0x180025bd0`
- `0x180025e40`
- `0x1800262b0`
- `0x180026300`
- `0x1800263c0`
- `0x1800268e0`
- `0x180026ad0`
- `0x18002a8a0`

## callees

- `0x180001fc4`
- `0x1800021c8`
- `0x180002916`

## import_xrefs

- `msvcrt!malloc` at `0x180001fde`
- `msvcrt!malloc` at `0x180001fde`

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
0x180001fc4  push    rbx
0x180001fc6  sub     rsp, 20h
0x180001fca  mov     rbx, rcx
0x180001fcd  jmp     short loc_180001FDE
0x180001fcf  mov     rcx, rbx; Size
0x180001fd2  call    _callnewh_0
0x180001fd7  test    eax, eax
0x180001fd9  jz      short loc_180001FEF
0x180001fdb  mov     rcx, rbx; Size
0x180001fde  call    cs:__imp_malloc
0x180001fe4  test    rax, rax
0x180001fe7  jz      short loc_180001FCF
0x180001fe9  add     rsp, 20h
0x180001fed  pop     rbx
0x180001fee  retn
0x180001fef  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
