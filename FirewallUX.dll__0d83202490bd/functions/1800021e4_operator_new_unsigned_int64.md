# operator new(unsigned __int64)

- ea: `0x1800021e4`
- end: `0x180002220`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `39`
- callee_count: `5`
- tags: ``

## callers

- `0x180002228`
- `0x180006810`
- `0x1800069e0`
- `0x18000b860`
- `0x18000c3e4`
- `0x18000c4f0`
- `0x18000c730`
- `0x18000c8c4`
- `0x18000e324`
- `0x18000e9d4`
- `0x18000eaa8`
- `0x180011b80`
- `0x180014cc0`
- `0x180015cfc`
- `0x180015e28`
- `0x1800175c0`
- `0x180017c70`
- `0x18001815c`
- `0x180018ac4`
- `0x180018bfc`
- `0x180018d50`
- `0x18001956c`
- `0x180019878`
- `0x180019d44`
- `0x18001a4ac`
- `0x18001a9e8`
- `0x18001b7e4`
- `0x18001ba40`
- `0x18001c870`
- `0x18001dfe0`
- `0x18001e0b0`
- `0x18001e940`
- `0x18001fd60`
- `0x1800209d4`
- `0x180021d68`
- `0x180022fd0`
- `0x180023310`
- `0x1800264d8`
- `0x180026618`

## callees

- `0x1800021e4`
- `0x180002800`
- `0x180002b46`
- `0x180002be0`
- `0x1800148f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800021e4  push    rbx
0x1800021e6  sub     rsp, 20h
0x1800021ea  mov     rbx, rcx
0x1800021ed  jmp     short loc_1800021FE
0x1800021ef  mov     rcx, rbx
0x1800021f2  call    _o__callnewh_0
0x1800021f7  test    eax, eax
0x1800021f9  jz      short loc_18000220E
0x1800021fb  mov     rcx, rbx; Size
0x1800021fe  call    _o_malloc_0
0x180002203  test    rax, rax
0x180002206  jz      short loc_1800021EF
0x180002208  add     rsp, 20h
0x18000220c  pop     rbx
0x18000220d  retn
0x18000220e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002212  jz      short loc_18000221A
0x180002214  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18000221a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
