# operator new(unsigned __int64)

- ea: `0x180002050`
- end: `0x18000208c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `5`
- tags: ``

## callers

- `0x180002440`
- `0x18000247c`
- `0x180004c34`
- `0x180004d44`
- `0x180004e80`
- `0x18000a2a0`
- `0x18000a3e0`
- `0x18000a518`
- `0x18000abe0`
- `0x18000ba70`
- `0x18000be34`
- `0x18000c4c8`

## callees

- `0x180002050`
- `0x180002680`
- `0x1800029b2`
- `0x180002a50`
- `0x18000c178`

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
0x180002050  push    rbx
0x180002052  sub     rsp, 20h
0x180002056  mov     rbx, rcx
0x180002059  jmp     short loc_18000206A
0x18000205b  mov     rcx, rbx
0x18000205e  call    _o__callnewh_0
0x180002063  test    eax, eax
0x180002065  jz      short loc_18000207A
0x180002067  mov     rcx, rbx; Size
0x18000206a  call    _o_malloc_0
0x18000206f  test    rax, rax
0x180002072  jz      short loc_18000205B
0x180002074  add     rsp, 20h
0x180002078  pop     rbx
0x180002079  retn
0x18000207a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000207e  jz      short loc_180002086
0x180002080  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002086  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
