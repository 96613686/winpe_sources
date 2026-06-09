# operator new(unsigned __int64)

- ea: `0x1800018a0`
- end: `0x1800018dc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `48`
- callee_count: `5`
- tags: ``

## callers

- `0x180002700`
- `0x180002b90`
- `0x180004808`
- `0x1800048f8`
- `0x1800049c8`
- `0x180004ab0`
- `0x18000b320`
- `0x18000b6c8`
- `0x18000bea8`
- `0x18000bf98`
- `0x18000c1bc`
- `0x18000c7d4`
- `0x18000cb90`
- `0x18000cd80`
- `0x18000d294`
- `0x18000d770`
- `0x18000eb20`
- `0x18000ec5c`
- `0x180011c74`
- `0x180013890`
- `0x180015c0c`
- `0x180015d34`
- `0x180015e40`
- `0x18001713c`
- `0x180018424`
- `0x18001877c`
- `0x180019140`
- `0x180019448`
- `0x18001a93c`
- `0x18001aac0`
- `0x18001ac28`
- `0x18001ad84`
- `0x18001af8c`
- `0x18001bc4c`
- `0x18001c4ac`
- `0x1800203c8`
- `0x180020508`
- `0x1800209b4`
- `0x180021d44`
- `0x180022848`
- `0x180022ca8`
- `0x180022ea4`
- `0x1800232b8`
- `0x180023434`
- `0x180023510`
- `0x1800239c0`
- `0x180024dcc`
- `0x180025ee4`

## callees

- `0x1800018a0`
- `0x180001f98`
- `0x18000232e`
- `0x1800023e4`
- `0x18000be50`

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
0x1800018a0  push    rbx
0x1800018a2  sub     rsp, 20h
0x1800018a6  mov     rbx, rcx
0x1800018a9  jmp     short loc_1800018BA
0x1800018ab  mov     rcx, rbx
0x1800018ae  call    _o__callnewh_0
0x1800018b3  test    eax, eax
0x1800018b5  jz      short loc_1800018CA
0x1800018b7  mov     rcx, rbx; Size
0x1800018ba  call    _o_malloc_0
0x1800018bf  test    rax, rax
0x1800018c2  jz      short loc_1800018AB
0x1800018c4  add     rsp, 20h
0x1800018c8  pop     rbx
0x1800018c9  retn
0x1800018ca  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800018ce  jz      short loc_1800018D6
0x1800018d0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800018d6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
