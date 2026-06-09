# operator new(unsigned __int64)

- ea: `0x18000260c`
- end: `0x180002648`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x1800077d8`
- `0x180007850`
- `0x180007c4c`
- `0x180007fc0`
- `0x180008134`
- `0x1800083ac`
- `0x180008514`
- `0x18000aa84`

## callees

- `0x18000260c`
- `0x180002e50`
- `0x180002ed6`
- `0x180002f70`
- `0x18000b278`

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
0x18000260c  push    rbx
0x18000260e  sub     rsp, 20h
0x180002612  mov     rbx, rcx
0x180002615  jmp     short loc_180002626
0x180002617  mov     rcx, rbx
0x18000261a  call    _o__callnewh_0
0x18000261f  test    eax, eax
0x180002621  jz      short loc_180002636
0x180002623  mov     rcx, rbx; Size
0x180002626  call    _o_malloc_0
0x18000262b  test    rax, rax
0x18000262e  jz      short loc_180002617
0x180002630  add     rsp, 20h
0x180002634  pop     rbx
0x180002635  retn
0x180002636  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000263a  jz      short loc_180002642
0x18000263c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002642  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
