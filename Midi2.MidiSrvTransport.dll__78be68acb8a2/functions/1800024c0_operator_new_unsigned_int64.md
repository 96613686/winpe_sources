# operator new(unsigned __int64)

- ea: `0x1800024c0`
- end: `0x1800024fc`
- name: `??2@YAPEAX_K@Z`
- size: `60`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800028b0`
- `0x1800028ec`
- `0x1800051e4`
- `0x1800052f4`
- `0x180005430`

## callees

- `0x1800024c0`
- `0x180002be4`
- `0x180002c0c`
- `0x180002f42`
- `0x180002fe0`

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
0x1800024c0  push    rbx
0x1800024c2  sub     rsp, 20h
0x1800024c6  mov     rbx, rcx
0x1800024c9  jmp     short loc_1800024DA
0x1800024cb  mov     rcx, rbx
0x1800024ce  call    _o__callnewh_0
0x1800024d3  test    eax, eax
0x1800024d5  jz      short loc_1800024EA
0x1800024d7  mov     rcx, rbx; Size
0x1800024da  call    _o_malloc_0
0x1800024df  test    rax, rax
0x1800024e2  jz      short loc_1800024CB
0x1800024e4  add     rsp, 20h
0x1800024e8  pop     rbx
0x1800024e9  retn
0x1800024ea  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800024ee  jz      short loc_1800024F6
0x1800024f0  call    ?__scrt_throw_std_bad_alloc@@YAXXZ; __scrt_throw_std_bad_alloc(void)
0x1800024f6  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
