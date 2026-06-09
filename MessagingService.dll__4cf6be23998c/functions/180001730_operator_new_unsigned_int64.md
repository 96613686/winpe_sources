# operator new(unsigned __int64)

- ea: `0x180001730`
- end: `0x180001761`
- name: `??2@YAPEAX_K@Z`
- size: `49`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180001908`
- `0x180002678`
- `0x180003090`
- `0x180004190`
- `0x18000422c`
- `0x1800042c8`
- `0x180004c48`
- `0x180006df0`
- `0x180007930`
- `0x180007c48`
- `0x18000a1c0`
- `0x18000ab00`

## callees

- `0x180001730`
- `0x180001a68`
- `0x18000269d`

## import_xrefs

- `msvcrt!malloc` at `0x18000174a`
- `msvcrt!malloc` at `0x18000174a`

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
0x180001730  push    rbx
0x180001732  sub     rsp, 20h
0x180001736  mov     rbx, rcx
0x180001739  jmp     short loc_18000174A
0x18000173b  mov     rcx, rbx; Size
0x18000173e  call    _callnewh_0
0x180001743  test    eax, eax
0x180001745  jz      short loc_18000175B
0x180001747  mov     rcx, rbx; Size
0x18000174a  call    cs:__imp_malloc
0x180001750  test    rax, rax
0x180001753  jz      short loc_18000173B
0x180001755  add     rsp, 20h
0x180001759  pop     rbx
0x18000175a  retn
0x18000175b  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
