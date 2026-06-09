# operator new(unsigned __int64)

- ea: `0x18000208c`
- end: `0x1800020c8`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `25`
- callee_count: `5`
- tags: ``

## callers

- `0x180001100`
- `0x1800020d0`
- `0x180005378`
- `0x1800068f0`
- `0x18000798c`
- `0x180008ae0`
- `0x18000b640`
- `0x18000cd80`
- `0x18000d414`
- `0x18000d740`
- `0x18000e664`
- `0x18000ee58`
- `0x18000f3a0`
- `0x18000f5c8`
- `0x180010fc0`
- `0x180011744`
- `0x18001187c`
- `0x1800119b0`
- `0x18001213c`
- `0x180012454`
- `0x180012924`
- `0x1800130b8`
- `0x180013784`
- `0x180014080`
- `0x180016c40`

## callees

- `0x18000208c`
- `0x180002c48`
- `0x180002d02`
- `0x180002da0`
- `0x1800072a8`

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
0x18000208c  push    rbx
0x18000208e  sub     rsp, 20h
0x180002092  mov     rbx, rcx
0x180002095  jmp     short loc_1800020A6
0x180002097  mov     rcx, rbx
0x18000209a  call    _o__callnewh_0
0x18000209f  test    eax, eax
0x1800020a1  jz      short loc_1800020B6
0x1800020a3  mov     rcx, rbx; Size
0x1800020a6  call    _o_malloc_0
0x1800020ab  test    rax, rax
0x1800020ae  jz      short loc_180002097
0x1800020b0  add     rsp, 20h
0x1800020b4  pop     rbx
0x1800020b5  retn
0x1800020b6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800020ba  jz      short loc_1800020C2
0x1800020bc  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800020c2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
