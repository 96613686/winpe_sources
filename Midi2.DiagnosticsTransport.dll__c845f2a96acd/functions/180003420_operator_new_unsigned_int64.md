# operator new(unsigned __int64)

- ea: `0x180003420`
- end: `0x18000345c`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180003810`
- `0x18000384c`
- `0x180006344`
- `0x180006454`
- `0x180006590`
- `0x18000c4c0`
- `0x18000c5cc`
- `0x18000c758`
- `0x18001148c`

## callees

- `0x180003420`
- `0x180003ff0`
- `0x1800040a2`
- `0x180004140`
- `0x180010038`

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
0x180003420  push    rbx
0x180003422  sub     rsp, 20h
0x180003426  mov     rbx, rcx
0x180003429  jmp     short loc_18000343A
0x18000342b  mov     rcx, rbx
0x18000342e  call    _o__callnewh_0
0x180003433  test    eax, eax
0x180003435  jz      short loc_18000344A
0x180003437  mov     rcx, rbx; Size
0x18000343a  call    _o_malloc_0
0x18000343f  test    rax, rax
0x180003442  jz      short loc_18000342B
0x180003444  add     rsp, 20h
0x180003448  pop     rbx
0x180003449  retn
0x18000344a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000344e  jz      short loc_180003456
0x180003450  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180003456  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
