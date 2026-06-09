# operator new(unsigned __int64)

- ea: `0x180015b14`
- end: `0x180015b50`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `32`
- callee_count: `5`
- tags: ``

## callers

- `0x180003000`
- `0x180003148`
- `0x180003398`
- `0x180004be0`
- `0x180006eb0`
- `0x180007be0`
- `0x1800088c8`
- `0x180008a6c`
- `0x180008c34`
- `0x18000960c`
- `0x18000a870`
- `0x18000b578`
- `0x18000b7cc`
- `0x18000b864`
- `0x18000c4c0`
- `0x18000dc30`
- `0x18000dcd4`
- `0x18000dd78`
- `0x18000e000`
- `0x18000e0a4`
- `0x18000e188`
- `0x18000e22c`
- `0x180010b84`
- `0x180011930`
- `0x18001324c`
- `0x1800137e4`
- `0x180013888`
- `0x180014174`
- `0x180014218`
- `0x180015f48`
- `0x1800178fc`
- `0x180018004`

## callees

- `0x180015b14`
- `0x180016440`
- `0x180016468`
- `0x18001651a`
- `0x180016592`

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
0x180015b14  push    rbx
0x180015b16  sub     rsp, 20h
0x180015b1a  mov     rbx, rcx
0x180015b1d  jmp     short loc_180015B2E
0x180015b1f  mov     rcx, rbx
0x180015b22  call    _o__callnewh_0
0x180015b27  test    eax, eax
0x180015b29  jz      short loc_180015B3E
0x180015b2b  mov     rcx, rbx; Size
0x180015b2e  call    _o_malloc_0
0x180015b33  test    rax, rax
0x180015b36  jz      short loc_180015B1F
0x180015b38  add     rsp, 20h
0x180015b3c  pop     rbx
0x180015b3d  retn
0x180015b3e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180015b42  jz      short loc_180015B4A
0x180015b44  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180015b4a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
