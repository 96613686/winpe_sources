# operator new(unsigned __int64)

- ea: `0x1800032c4`
- end: `0x180003300`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `61`
- callee_count: `5`
- tags: ``

## callers

- `0x180002040`
- `0x180002620`
- `0x180003308`
- `0x1800058d8`
- `0x1800084d0`
- `0x18000bdd0`
- `0x18000c164`
- `0x180014c24`
- `0x180014e38`
- `0x180014f2c`
- `0x1800151a0`
- `0x180015728`
- `0x180015dfc`
- `0x180016974`
- `0x18001757c`
- `0x180019c9c`
- `0x18001a1ec`
- `0x18001a9e0`
- `0x18001ae64`
- `0x18001b9b4`
- `0x18001bcac`
- `0x18001cc98`
- `0x18001cd58`
- `0x18001cdb8`
- `0x18001d120`
- `0x18001d228`
- `0x18001d4cc`
- `0x18001d748`
- `0x18001da04`
- `0x18001db94`
- `0x18001dbe8`
- `0x18001decc`
- `0x18001e4dc`
- `0x18001e600`
- `0x18001e6d0`
- `0x18001eaa4`
- `0x18001eb34`
- `0x18001f08c`
- `0x180020f84`
- `0x180021a80`
- `0x180021c30`
- `0x180021f78`
- `0x1800220a4`
- `0x180022228`
- `0x1800224d8`
- `0x1800240c0`
- `0x1800243b0`
- `0x180024550`
- `0x180024814`
- `0x1800251a0`

## callees

- `0x1800032c4`
- `0x180003908`
- `0x180003c52`
- `0x180003cf0`
- `0x18000a970`

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
0x1800032c4  push    rbx
0x1800032c6  sub     rsp, 20h
0x1800032ca  mov     rbx, rcx
0x1800032cd  jmp     short loc_1800032DE
0x1800032cf  mov     rcx, rbx
0x1800032d2  call    _o__callnewh_0
0x1800032d7  test    eax, eax
0x1800032d9  jz      short loc_1800032EE
0x1800032db  mov     rcx, rbx; Size
0x1800032de  call    _o_malloc_0
0x1800032e3  test    rax, rax
0x1800032e6  jz      short loc_1800032CF
0x1800032e8  add     rsp, 20h
0x1800032ec  pop     rbx
0x1800032ed  retn
0x1800032ee  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800032f2  jz      short loc_1800032FA
0x1800032f4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800032fa  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
