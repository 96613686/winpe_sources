# operator new(unsigned __int64)

- ea: `0x18001cf74`
- end: `0x18001cfb0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `38`
- callee_count: `5`
- tags: ``

## callers

- `0x180006e00`
- `0x180007700`
- `0x180007880`
- `0x180008230`
- `0x180009070`
- `0x180009740`
- `0x18000fc10`
- `0x180010560`
- `0x180010bb0`
- `0x180010cd0`
- `0x180012b8c`
- `0x18001305c`
- `0x180013f60`
- `0x180014d60`
- `0x180015cc0`
- `0x1800191ec`
- `0x180019340`
- `0x180019734`
- `0x18001a198`
- `0x18001a310`
- `0x18001b9c8`
- `0x18001c17c`
- `0x18001c824`
- `0x18001c9e4`
- `0x18001d39c`
- `0x18001ddf0`
- `0x18001e314`
- `0x18001e5b4`
- `0x18001f870`
- `0x18001fa54`
- `0x18001fea0`
- `0x1800208bc`
- `0x180020a6c`
- `0x180020cd0`
- `0x180020fc4`
- `0x180021410`
- `0x1800217e4`
- `0x180021920`

## callees

- `0x18001cf74`
- `0x18001d570`
- `0x18001d598`
- `0x18001d8de`
- `0x18001d970`

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
0x18001cf74  push    rbx
0x18001cf76  sub     rsp, 20h
0x18001cf7a  mov     rbx, rcx
0x18001cf7d  jmp     short loc_18001CF8E
0x18001cf7f  mov     rcx, rbx
0x18001cf82  call    _o__callnewh_0
0x18001cf87  test    eax, eax
0x18001cf89  jz      short loc_18001CF9E
0x18001cf8b  mov     rcx, rbx; Size
0x18001cf8e  call    _o_malloc_0
0x18001cf93  test    rax, rax
0x18001cf96  jz      short loc_18001CF7F
0x18001cf98  add     rsp, 20h
0x18001cf9c  pop     rbx
0x18001cf9d  retn
0x18001cf9e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001cfa2  jz      short loc_18001CFAA
0x18001cfa4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x18001cfaa  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
