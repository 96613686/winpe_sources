# operator new(unsigned __int64)

- ea: `0x180002cfc`
- end: `0x180002d38`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `90`
- callee_count: `5`
- tags: ``

## callers

- `0x180002d40`
- `0x180003730`
- `0x180003aa0`
- `0x180003c30`
- `0x180003df0`
- `0x180003f60`
- `0x1800040f0`
- `0x180004260`
- `0x1800044a0`
- `0x1800048c0`
- `0x180004b60`
- `0x180004ce0`
- `0x1800050b0`
- `0x1800052d0`
- `0x180005380`
- `0x180005620`
- `0x180005880`
- `0x1800059a0`
- `0x1800059f0`
- `0x180005a50`
- `0x180005ac0`
- `0x180005bd0`
- `0x180005c40`
- `0x180006630`
- `0x1800066a0`
- `0x180006700`
- `0x180006770`
- `0x180006b10`
- `0x180008230`
- `0x180008350`
- `0x180010464`
- `0x1800104cc`
- `0x180010534`
- `0x18001059c`
- `0x180010604`
- `0x18001066c`
- `0x1800106d4`
- `0x180010730`
- `0x1800107a4`
- `0x18001080c`
- `0x180012100`
- `0x1800121a0`
- `0x180012220`
- `0x1800125a0`
- `0x1800126d0`
- `0x180012740`
- `0x1800127c0`
- `0x1800128c0`
- `0x180012950`
- `0x180012a60`

## callees

- `0x180002cfc`
- `0x18000329c`
- `0x18000333e`
- `0x1800033d0`
- `0x18001c7f4`

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
0x180002cfc  push    rbx
0x180002cfe  sub     rsp, 20h
0x180002d02  mov     rbx, rcx
0x180002d05  jmp     short loc_180002D16
0x180002d07  mov     rcx, rbx
0x180002d0a  call    _o__callnewh_0
0x180002d0f  test    eax, eax
0x180002d11  jz      short loc_180002D26
0x180002d13  mov     rcx, rbx; Size
0x180002d16  call    _o_malloc_0
0x180002d1b  test    rax, rax
0x180002d1e  jz      short loc_180002D07
0x180002d20  add     rsp, 20h
0x180002d24  pop     rbx
0x180002d25  retn
0x180002d26  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180002d2a  jz      short loc_180002D32
0x180002d2c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002d32  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
