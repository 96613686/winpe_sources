# operator new(unsigned __int64)

- ea: `0x18000145c`
- end: `0x180001495`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x18000149c`
- `0x180003b80`
- `0x180003bd0`
- `0x180008fb0`
- `0x180009248`
- `0x180009fb4`
- `0x180012df4`
- `0x18001faf0`
- `0x18001fdf4`

## callees

- `0x18000145c`
- `0x1800020d6`
- `0x180002150`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = o_malloc_0(Size);
    if ( v2 || !(unsigned int)o__callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x18000145c  mov     [rsp+arg_0], rbx
0x180001461  push    rdi
0x180001462  sub     rsp, 20h
0x180001466  mov     rdi, rcx
0x180001469  jmp     short loc_18000147A
0x18000146b  mov     rcx, rdi
0x18000146e  call    _o__callnewh_0
0x180001473  test    eax, eax
0x180001475  jz      short loc_180001487
0x180001477  mov     rcx, rdi; Size
0x18000147a  call    _o_malloc_0
0x18000147f  mov     rbx, rax
0x180001482  test    rax, rax
0x180001485  jz      short loc_18000146B
0x180001487  mov     rax, rbx
0x18000148a  mov     rbx, [rsp+28h+arg_0]
0x18000148f  add     rsp, 20h
0x180001493  pop     rdi
0x180001494  retn
```
