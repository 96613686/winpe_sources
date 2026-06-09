# operator new(unsigned __int64)

- ea: `0x18000294c`
- end: `0x180002988`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180001e50`
- `0x180001f10`
- `0x180001fd0`
- `0x180002090`
- `0x180002990`
- `0x18000819c`
- `0x180008d44`
- `0x18000bbc4`
- `0x18000c580`

## callees

- `0x18000294c`
- `0x180002e64`
- `0x180002f02`
- `0x180002fac`
- `0x18000c110`

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
0x18000294c  push    rbx
0x18000294e  sub     rsp, 20h
0x180002952  mov     rbx, rcx
0x180002955  jmp     short loc_180002966
0x180002957  mov     rcx, rbx
0x18000295a  call    _o__callnewh_0
0x18000295f  test    eax, eax
0x180002961  jz      short loc_180002976
0x180002963  mov     rcx, rbx; Size
0x180002966  call    _o_malloc_0
0x18000296b  test    rax, rax
0x18000296e  jz      short loc_180002957
0x180002970  add     rsp, 20h
0x180002974  pop     rbx
0x180002975  retn
0x180002976  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000297a  jz      short loc_180002982
0x18000297c  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x180002982  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
