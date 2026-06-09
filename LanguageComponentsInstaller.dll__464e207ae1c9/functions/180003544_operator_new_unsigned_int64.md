# operator new(unsigned __int64)

- ea: `0x180003544`
- end: `0x180003580`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `48`
- callee_count: `5`
- tags: ``

## callers

- `0x180003588`
- `0x1800058dc`
- `0x180005a14`
- `0x18000a940`
- `0x18000bc70`
- `0x18000c15c`
- `0x18000ca94`
- `0x18000cca4`
- `0x18000cef4`
- `0x18000d11c`
- `0x18000d2b4`
- `0x18000d4a8`
- `0x18000e764`
- `0x18000ebfc`
- `0x18000ed90`
- `0x18000ef00`
- `0x18000f808`
- `0x18000fd14`
- `0x180010244`
- `0x180010e3c`
- `0x180011038`
- `0x180011308`
- `0x18001142c`
- `0x180017a80`
- `0x180019168`
- `0x18001d460`
- `0x18001d520`
- `0x18001d5c0`
- `0x18001d6c8`
- `0x18001d96c`
- `0x18001dbe8`
- `0x18001dea4`
- `0x18001dfdc`
- `0x18001e16c`
- `0x18001e1c0`
- `0x18001e60c`
- `0x18001ec00`
- `0x18001ed30`
- `0x18001eee0`
- `0x18001f004`
- `0x18001fcfc`
- `0x18001ff8c`
- `0x180020fc0`
- `0x180022340`
- `0x1800247bc`
- `0x18002621c`
- `0x1800263b4`
- `0x1800268d4`

## callees

- `0x180003544`
- `0x180003f78`
- `0x180004032`
- `0x1800040dc`
- `0x18000a81c`

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
0x180003544  push    rbx
0x180003546  sub     rsp, 20h
0x18000354a  mov     rbx, rcx
0x18000354d  jmp     short loc_18000355E
0x18000354f  mov     rcx, rbx
0x180003552  call    _o__callnewh_0
0x180003557  test    eax, eax
0x180003559  jz      short loc_18000356E
0x18000355b  mov     rcx, rbx; Size
0x18000355e  call    _o_malloc_0
0x180003563  test    rax, rax
0x180003566  jz      short loc_18000354F
0x180003568  add     rsp, 20h
0x18000356c  pop     rbx
0x18000356d  retn
0x18000356e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180003572  jz      short loc_18000357A
0x180003574  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000357a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
