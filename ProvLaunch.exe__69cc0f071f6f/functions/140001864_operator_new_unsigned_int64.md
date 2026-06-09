# operator new(unsigned __int64)

- ea: `0x140001864`
- end: `0x140001895`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x1400061e0`
- `0x140006230`
- `0x140006278`
- `0x14000693c`
- `0x140006b5c`
- `0x140007b38`
- `0x140007d20`
- `0x140009328`
- `0x14000937c`
- `0x14000a937`
- `0x14000ae13`

## callees

- `0x140001864`
- `0x140001cd6`
- `0x140001ce2`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000188e`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000188e`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = malloc_0(Size);
    if ( result )
      break;
    if ( !callnewh_0(i) )
    {
      std::_Xbad_alloc();
      JUMPOUT(0x140001894LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140001864  push    rbx
0x140001866  sub     rsp, 20h
0x14000186a  mov     rbx, rcx
0x14000186d  jmp     short loc_14000187E
0x14000186f  mov     rcx, rbx; Size
0x140001872  call    _callnewh_0
0x140001877  test    eax, eax
0x140001879  jz      short loc_14000188E
0x14000187b  mov     rcx, rbx; Size
0x14000187e  call    malloc_0
0x140001883  test    rax, rax
0x140001886  jz      short loc_14000186F
0x140001888  add     rsp, 20h
0x14000188c  pop     rbx
0x14000188d  retn
0x14000188e  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
