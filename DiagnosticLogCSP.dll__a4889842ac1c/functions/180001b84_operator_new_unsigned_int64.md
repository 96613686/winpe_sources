# operator new(unsigned __int64)

- ea: `0x180001b84`
- end: `0x180001bc0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `52`
- callee_count: `5`
- tags: ``

## callers

- `0x180002b88`
- `0x180002c44`
- `0x1800030e0`
- `0x1800032a0`
- `0x18000a368`
- `0x18000c410`
- `0x180010678`
- `0x180012238`
- `0x180015898`
- `0x180015988`
- `0x180015a58`
- `0x180015b40`
- `0x18001c6d8`
- `0x18001cdc8`
- `0x18001ceb8`
- `0x18001d0dc`
- `0x18001d5fc`
- `0x18001d878`
- `0x18001da68`
- `0x18001deac`
- `0x18001e388`
- `0x18001f744`
- `0x18001f880`
- `0x1800228a4`
- `0x18002476c`
- `0x180026a08`
- `0x180026b30`
- `0x180026c3c`
- `0x180027f40`
- `0x180029224`
- `0x18002957c`
- `0x180029f44`
- `0x18002a248`
- `0x18002ae04`
- `0x18002af88`
- `0x18002b0f0`
- `0x18002b24c`
- `0x18002b9d0`
- `0x18002bbf4`
- `0x18002d818`
- `0x18002da58`
- `0x18002df44`
- `0x18002f2e4`
- `0x18002fdf8`
- `0x1800302f0`
- `0x18003050c`
- `0x180030920`
- `0x180030a94`
- `0x180030b70`
- `0x180031020`

## callees

- `0x180001b84`
- `0x180002188`
- `0x18000252e`
- `0x1800025d8`
- `0x18000bb3c`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rbx
  void *result; // rax

  for ( i = Size; ; Size = i )
  {
    result = o_malloc_0(Size);
    if ( result )
      break;
    if ( !(unsigned int)o__callnewh_0(i) )
    {
      if ( i != -1 )
        __scrt_throw_std_bad_alloc();
      __scrt_throw_std_bad_array_new_length();
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001b84  push    rbx
0x180001b86  sub     rsp, 20h
0x180001b8a  mov     rbx, rcx
0x180001b8d  jmp     short loc_180001B9E
0x180001b8f  mov     rcx, rbx
0x180001b92  call    _o__callnewh_0
0x180001b97  test    eax, eax
0x180001b99  jz      short loc_180001BAE
0x180001b9b  mov     rcx, rbx; Size
0x180001b9e  call    _o_malloc_0
0x180001ba3  test    rax, rax
0x180001ba6  jz      short loc_180001B8F
0x180001ba8  add     rsp, 20h
0x180001bac  pop     rbx
0x180001bad  retn
0x180001bae  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001bb2  jz      short loc_180001BBA
0x180001bb4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001bba  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
