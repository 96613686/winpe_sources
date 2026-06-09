# operator new(unsigned __int64)

- ea: `0x18000123c`
- end: `0x18000126d`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x180001230`
- `0x180001418`
- `0x180002974`
- `0x180004a88`
- `0x180004be0`
- `0x1800051b4`
- `0x18000a394`
- `0x18000aa18`
- `0x18000cc24`
- `0x18000d66c`
- `0x18000d6ac`
- `0x18000f494`
- `0x18000f4d4`
- `0x18000fd43`

## callees

- `0x18000123c`
- `0x180001578`
- `0x180002535`

## import_xrefs

- `msvcrt!malloc` at `0x180001256`
- `msvcrt!malloc` at `0x180001256`

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
0x18000123c  push    rbx
0x18000123e  sub     rsp, 20h
0x180001242  mov     rbx, rcx
0x180001245  jmp     short loc_180001256
0x180001247  mov     rcx, rbx; Size
0x18000124a  call    _callnewh_0
0x18000124f  test    eax, eax
0x180001251  jz      short loc_180001267
0x180001253  mov     rcx, rbx; Size
0x180001256  call    cs:__imp_malloc
0x18000125c  test    rax, rax
0x18000125f  jz      short loc_180001247
0x180001261  add     rsp, 20h
0x180001265  pop     rbx
0x180001266  retn
0x180001267  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
