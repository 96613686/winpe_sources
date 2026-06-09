# operator new(unsigned __int64)

- ea: `0x1800021fc`
- end: `0x180002238`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `14`
- callee_count: `5`
- tags: ``

## callers

- `0x1800021ac`
- `0x1800022b4`
- `0x180009508`
- `0x180009820`
- `0x180009a08`
- `0x18000b11c`
- `0x18000c01c`
- `0x18000e2c4`
- `0x18000e414`
- `0x18000e5a0`
- `0x18000e7f0`
- `0x18000e90c`
- `0x18000f224`
- `0x180010d1c`

## callees

- `0x180002076`
- `0x18000211c`
- `0x1800021fc`
- `0x1800022e8`
- `0x18000b408`

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
0x1800021fc  push    rbx
0x1800021fe  sub     rsp, 20h
0x180002202  mov     rbx, rcx
0x180002205  jmp     short loc_180002216
0x180002207  mov     rcx, rbx
0x18000220a  call    _o__callnewh_0
0x18000220f  test    eax, eax
0x180002211  jz      short loc_180002226
0x180002213  mov     rcx, rbx; Size
0x180002216  call    _o_malloc_0
0x18000221b  test    rax, rax
0x18000221e  jz      short loc_180002207
0x180002220  add     rsp, 20h
0x180002224  pop     rbx
0x180002225  retn
0x180002226  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000222a  jz      short loc_180002232
0x18000222c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002232  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
