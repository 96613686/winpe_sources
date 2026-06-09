# operator new(unsigned __int64)

- ea: `0x1800018f4`
- end: `0x180001925`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180001e08`
- `0x18000254c`
- `0x18000645c`
- `0x180009430`
- `0x18000a034`
- `0x18000a1c4`
- `0x18000a94c`
- `0x18000b8f8`
- `0x18000c22c`
- `0x18000c7e4`
- `0x18000e184`
- `0x18000f574`
- `0x18000fc90`
- `0x1800116e7`
- `0x1800119be`

## callees

- `0x1800018f4`
- `0x180001f66`
- `0x180001f72`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000191e`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000191e`

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
      JUMPOUT(0x180001924LL);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800018f4  push    rbx
0x1800018f6  sub     rsp, 20h
0x1800018fa  mov     rbx, rcx
0x1800018fd  jmp     short loc_18000190E
0x1800018ff  mov     rcx, rbx; Size
0x180001902  call    _callnewh_0
0x180001907  test    eax, eax
0x180001909  jz      short loc_18000191E
0x18000190b  mov     rcx, rbx; Size
0x18000190e  call    malloc_0
0x180001913  test    rax, rax
0x180001916  jz      short loc_1800018FF
0x180001918  add     rsp, 20h
0x18000191c  pop     rbx
0x18000191d  retn
0x18000191e  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
