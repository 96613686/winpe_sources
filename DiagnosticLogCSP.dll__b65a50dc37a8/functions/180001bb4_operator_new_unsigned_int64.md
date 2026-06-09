# operator new(unsigned __int64)

- ea: `0x180001bb4`
- end: `0x180001bf0`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `52`
- callee_count: `5`
- tags: ``

## callers

- `0x180002bb8`
- `0x180002c74`
- `0x180003140`
- `0x180003300`
- `0x18000a68c`
- `0x18000c980`
- `0x180010ed4`
- `0x180012bf8`
- `0x18001641c`
- `0x18001650c`
- `0x1800165dc`
- `0x1800166c8`
- `0x18001d5ec`
- `0x18001dd58`
- `0x18001de4c`
- `0x18001e074`
- `0x18001e594`
- `0x18001e810`
- `0x18001ea00`
- `0x18001ee48`
- `0x18001f32c`
- `0x180020760`
- `0x1800208a0`
- `0x180023844`
- `0x1800258d4`
- `0x180027b70`
- `0x180027ca8`
- `0x180027db4`
- `0x18002913c`
- `0x18002a3fc`
- `0x18002a768`
- `0x18002b1c4`
- `0x18002b4c8`
- `0x18002c0d8`
- `0x18002c25c`
- `0x18002c3c4`
- `0x18002c520`
- `0x18002cce0`
- `0x18002cf08`
- `0x18002eb78`
- `0x18002edd0`
- `0x18002f374`
- `0x1800306f4`
- `0x18003126c`
- `0x18003178c`
- `0x1800319b0`
- `0x180031e30`
- `0x180031fa4`
- `0x180032080`
- `0x180032580`

## callees

- `0x180001bb4`
- `0x1800021b8`
- `0x18000255e`
- `0x180002608`
- `0x18000c07c`

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
0x180001bb4  push    rbx
0x180001bb6  sub     rsp, 20h
0x180001bba  mov     rbx, rcx
0x180001bbd  jmp     short loc_180001BCE
0x180001bbf  mov     rcx, rbx
0x180001bc2  call    _o__callnewh_0
0x180001bc7  test    eax, eax
0x180001bc9  jz      short loc_180001BDE
0x180001bcb  mov     rcx, rbx; Size
0x180001bce  call    _o_malloc_0
0x180001bd3  test    rax, rax
0x180001bd6  jz      short loc_180001BBF
0x180001bd8  add     rsp, 20h
0x180001bdc  pop     rbx
0x180001bdd  retn
0x180001bde  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180001be2  jz      short loc_180001BEA
0x180001be4  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180001bea  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
