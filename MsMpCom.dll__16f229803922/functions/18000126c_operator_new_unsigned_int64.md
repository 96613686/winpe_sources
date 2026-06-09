# operator new(unsigned __int64)

- ea: `0x18000126c`
- end: `0x18000129d`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180001260`
- `0x180002188`
- `0x180003060`
- `0x180003514`
- `0x180003668`
- `0x180003790`
- `0x1800038bc`
- `0x1800039bc`
- `0x180007fdc`
- `0x180008238`
- `0x180009b34`

## callees

- `0x18000126c`
- `0x180001418`
- `0x180001c6c`

## import_xrefs

- `msvcrt!malloc` at `0x180001286`
- `msvcrt!malloc` at `0x180001286`

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
0x18000126c  push    rbx
0x18000126e  sub     rsp, 20h
0x180001272  mov     rbx, rcx
0x180001275  jmp     short loc_180001286
0x180001277  mov     rcx, rbx; Size
0x18000127a  call    _callnewh_0
0x18000127f  test    eax, eax
0x180001281  jz      short loc_180001297
0x180001283  mov     rcx, rbx; Size
0x180001286  call    cs:__imp_malloc
0x18000128c  test    rax, rax
0x18000128f  jz      short loc_180001277
0x180001291  add     rsp, 20h
0x180001295  pop     rbx
0x180001296  retn
0x180001297  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
