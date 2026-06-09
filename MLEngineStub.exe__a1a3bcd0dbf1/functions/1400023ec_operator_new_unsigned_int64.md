# operator new(unsigned __int64)

- ea: `0x1400023ec`
- end: `0x140002428`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x140007020`
- `0x140007098`
- `0x1400074b8`
- `0x14000782c`
- `0x1400079a0`
- `0x140007c18`
- `0x140007d80`
- `0x14000a678`

## callees

- `0x1400023ec`
- `0x140002ab4`
- `0x140002b5e`
- `0x140002c40`
- `0x14000a1a8`

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
0x1400023ec  push    rbx
0x1400023ee  sub     rsp, 20h
0x1400023f2  mov     rbx, rcx
0x1400023f5  jmp     short loc_140002406
0x1400023f7  mov     rcx, rbx
0x1400023fa  call    _o__callnewh_0
0x1400023ff  test    eax, eax
0x140002401  jz      short loc_140002416
0x140002403  mov     rcx, rbx; Size
0x140002406  call    _o_malloc_0
0x14000240b  test    rax, rax
0x14000240e  jz      short loc_1400023F7
0x140002410  add     rsp, 20h
0x140002414  pop     rbx
0x140002415  retn
0x140002416  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000241a  jz      short loc_140002422
0x14000241c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x140002422  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
